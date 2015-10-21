1. Install ansible
	brew install ansible
2. Modify hosts file
	[nagios-server]
	192.168.59.103 //nagios sever here

	[nagios-agents]
	192.168.59.105 //nagios agent here
3. Run playbook
	ansible-playbook deploy.yml -i hosts --ask-pass -K	