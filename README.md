##1. Install ansible
	brew install ansible
##2. Modify hosts file
	[nagios-server]
	192.168.59.103 //nagios sever here

	[nagios-agents]
	192.168.59.105 //nagios agent here
##3. Add target configuration file
	//In target-configurations/clients.cfg
	define host {
		use                             linux-server
		host_name                       nagios-agent-1
		alias                           nagios-agent
		address                         192.168.59.105
		max_check_attempts              5
		check_period                    24x7
		notification_interval           30
		notification_period             24x7
	}	
##4. Run playbook
	ansible-playbook deploy.yml -i hosts --ask-pass -K
##5. Visit ngios server
	http://{nagios-server}/nagios