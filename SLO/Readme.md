# Deploy SLO for Management Zone

Export the variable
	 export MZ=[MZ-name]

Deploy the configuration
	cd;cd quickstart-ace-configurator;
	./monaco deploy -e=environments.yaml SLO/deploy-step1
	./monaco deploy -e=environments.yaml SLO/deploy-step2
