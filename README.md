# jenkins-project
jenkins-project
# 📘 Jenkins CI/CD Pipeline Project
________________________________________
# Project Overview (Single Passage)
**This project involves building a complete end-to-end CI/CD pipeline using Jenkins with a Master–Agent architecture on AWS. The source code is maintained in a GitHub repository, which Jenkins pulls automatically during pipeline execution. A Jenkins agent running on a separate EC2 instance performs the build and deployment tasks. The final output is deployed to a target EC2 instance running an Nginx web server. The project emphasizes real-world DevOps practices such as secure SSH authentication, non-interactive automation, proper file transfer mechanisms, and systematic debugging. Multiple issues were encountered during implementation, including Jenkins accessibility problems, Git and plugin misconfigurations, SSH authentication failures, and deployment logic errors. Each issue was identified, analyzed, and resolved step by step, resulting in a stable, production-style CI/CD pipeline.**
________________________________________
# Step-by-Step Implementation 
•	Launched an EC2 instance and installed Jenkins to act as the Jenkins Master
•	Opened required ports (22, 8080) in the EC2 security group
•	Completed Jenkins initial setup and plugin installation
•	Launched a second EC2 instance and configured it as a Jenkins Agent
•	Installed Java and Git on the Jenkins Agent
•	Connected the agent to the Jenkins Master using SSH
•	Created a GitHub repository containing application code and a Jenkinsfile
•	Configured Jenkins to pull the Jenkinsfile directly from GitHub
•	Installed required Jenkins plugins (Git, Pipeline, SSH Agent)
•	Created Jenkins SSH credentials for secure EC2 access
•	Designed a declarative Jenkins pipeline with checkout, build, and deploy stages
•	Used SCP to transfer files from Jenkins Agent to the target EC2 instance
•	Deployed the application to the Nginx web directory on the target EC2
•	Validated deployment by accessing the application through a browser
________________________________________
# Errors Faced and Solutions 
•	Jenkins UI not accessible
    → Resolved by opening port 8080 in the EC2 security group
•	GitHub checkout failure (git ls-remote error)
    → Installed Git on both Jenkins Master and Agent instances
•	sshagent DSL method not found
    → Installed the SSH Agent Plugin and restarted Jenkins
•	SSH authentication failure between Jenkins and EC2
    → Configured passwordless SSH using Jenkins credentials
•	Host key verification failed during pipeline execution
    → Disabled strict host key checking for non-interactive SSH commands
•	Deployment failed using cp command
    → Identified that files existed only on Jenkins Agent
    → Replaced cp with scp to transfer files before deployment
•	Shell script errors due to heredoc usage
    → Simplified SSH commands to avoid heredoc syntax issues
________________________________________
# Key Outcome
•	Successfully built a stable Jenkins CI/CD pipeline
•	Implemented secure and automated EC2 deployment
•	Gained hands-on experience with real DevOps troubleshooting
•	Applied best practices to minimize errors and improve pipeline reliability
