AWS EC2 Security, SSH, and Access Control Labs

Overview

This project documents hands-on labs focused on deploying, accessing, securing, and troubleshooting a cloud-based virtual machine using AWS EC2. The labs simulate real-world scenarios including SSH access issues, configuration errors, security hardening, and log monitoring.

The goal of this project is to build foundational skills in cloud security, Linux administration, and troubleshooting within a live environment.

⸻
Environment
	•	AWS EC2 (Amazon Linux)
	•	SSH
	•	PowerShell
	•	Nano (Linux text editor)
	•	AWS Security Groups
⸻
Lab 1: EC2 Deployment and Initial Access

What I Did
	•	Launched an EC2 instance using AWS
	•	Generated and downloaded a key pair (.pem)
	•	Configured Security Group to allow SSH (port 22)
	•	Attempted remote connection using SSH

Challenges

Permission Denied (publickey)
Fix
icacls Lab1.pem /grant:r <username>:(R)
Incorrect SSH Command Formatting
Fix
ssh -i Lab1.pem ec2-user@<public-ip>
Result
	•	Successfully connected to EC2 instance
	•	Learned how SSH key authentication works
	•	Understood importance of file permissions

⸻

Lab 2: SSH Troubleshooting and Key Management

What I Did
	•	Retried SSH connections after failures
	•	Adjusted key permissions
	•	Verified correct login user (ec2-user)

Challenges

Incorrect Username Usage
	•	Confusion between system username vs EC2 default user

Fix
ec2-user
Result
	•	Established reliable SSH access
	•	Improved troubleshooting skills
	•	Understood authentication flow

⸻

Lab 3: SSH Configuration and Hardening

What I Did
	•	Opened SSH config file:
  sudo nano /etc/ssh/sshd_config
  •	Attempted to modify SSH settings
	•	Restarted SSH service

Challenges

Saving in Nano
	•	Initially unsure how to save changes

Fix
	•	CTRL + O (save)
	•	CTRL + X (exit)

SSH Restart Failure
control process exited with error code
Result
	•	Learned how to edit Linux config files
	•	Understood risks of misconfiguring SSH
	•	Gained experience with system services

⸻

Lab 4: Log Monitoring and Access Observation

What I Did
	•	Observed login attempts on the server
	•	Simulated failed login attempts
	•	Reviewed authentication logs

Key Concepts Learned
	•	Servers log all login activity
	•	Failed attempts can indicate attacks
	•	Logs are essential for monitoring

Result
	•	Gained insight into system logging
	•	Understood attacker behavior patterns
	•	Built foundation for detection labs

⸻

Lab 5: Instance Security and Access Control

What I Did
	•	Modified AWS Security Group rules
	•	Restricted SSH access
	•	Locked down instance after testing

Key Concepts Learned
	•	Security Groups act as a firewall
	•	Open ports increase risk
	•	Restricting access improves security

Result
	•	Improved cloud security awareness
	•	Learned to reduce attack surface
	•	Practiced securing active infrastructure

⸻

Lab 6: SSH Port Change Attempt (Port 2222)

What I Did
	•	Edited SSH configuration:
  sudo nano /etc/ssh/sshd_confi
  Changed 
  Port 22
  To Port 2222
  Restarted SSH service
	•	Attempted to reconnect using new port

Issue

Connection Failure on Port 2222
ssh -i Lab1.pem ec2-user@<public-ip> -p 2222
Root Causes
	•	Port 2222 not opened in AWS Security Group
	•	SSH restarted before verifying configuration
	•	Risk of remote lockout during changes

Key Lessons Learned
	•	Always open new ports before restarting services
	•	Misconfigurations can break remote access
	•	SSH hardening must be done carefully in cloud environments

Result
	•	Gained real-world troubleshooting experience
	•	Understood risks of remote configuration changes
	•	Learned proper SSH hardening process

⸻

Skills Demonstrated
	•	AWS EC2 deployment and configuration
	•	SSH authentication and remote access
	•	Linux system administration
	•	Troubleshooting connectivity and permission issues
	•	Cloud security fundamentals
	•	Log monitoring and threat awareness
	•	Firewall and access control management
	[CloudWatch Lab Steps](CloudWatch_Lab.md)
