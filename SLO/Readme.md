# Automatically deploy SLOs per management zone
![image](https://user-images.githubusercontent.com/40337213/176840959-2778974b-950c-49bb-b79e-8f5bbfce94a0.png)


## Prerequisite
- [Install-Ace-Configurator](/Install-Ace-Configurator)
	
## Export the variable:

	 export MZ=[MZ-name]

## Deploy Slo:

	cd;cd quickstart-ace-configurator;
	./monaco deploy -e=environments.yaml SLO/deploy-step1
	./monaco deploy -e=environments.yaml SLO/deploy-step2


## Dashboard :
 import **Dynatrace_Simple Smarter** to have slo dashboard for management zone centric view :
 	https://dynatrace.github.io/BizOpsConfigurator/index.html#downloadExcel

Dynatrace_Simply Smarter home page
![image](https://user-images.githubusercontent.com/40337213/176837340-187a05bb-ef54-401a-92d2-77f15eadc503.png)

SLO management zone centric
![image](https://user-images.githubusercontent.com/40337213/176890303-94327dd3-f884-4e16-9066-e8516b7f6750.png)

Analyze view
![image](https://user-images.githubusercontent.com/40337213/176999225-1b6e9924-6d0f-4e78-89b7-c74220cde85a.png)
	
## Default configuration:  
![image](https://user-images.githubusercontent.com/40337213/176948834-a602780f-49b9-4e0a-ad64-5caf1d19fa3c.png)

- to disable a slo from monaco, open slo/slo.yaml and comment the line: 
<img src="https://user-images.githubusercontent.com/40337213/176834195-e5676e9c-25bc-41e8-b094-87c9c053c1f1.png" width="600" height="200">

- to change the threshold, open the slo/xxx.json and modify the value : 
![image](https://user-images.githubusercontent.com/40337213/176834354-fb68c020-7b7c-4a83-b518-92736ddaac9a.png)
