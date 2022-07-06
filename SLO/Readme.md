# Automatically deploy SLOs per management zone
![image](https://user-images.githubusercontent.com/40337213/176840959-2778974b-950c-49bb-b79e-8f5bbfce94a0.png)


## Prerequisite
- [Install-Ace-Configurator](/Install-Ace-Configurator) which describes how to install monaco
	
## Export variables:

	export NEW_CLI=1
	export MyTenant={your-environment-id}.live.dynatrace.com or {your-domain}/e/{your-environment-id}
	export MyToken=yyyy
	export SLO_PREFIX=[mzname without space and without special character]
	export MZID=[mzid]

for example: 

	export NEW_CLI=1
	export MyTenant=abc123.live.dynatrace.com
	export MyToken=dt0c01.ABCDEFGHIJ0123456789	#API modules SLO wirtes + configuraton Writes
	export SLO_PREFIX=easytravel01
	export MZID=8895610195457057204


## Deploy with monaco:

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
![image](https://user-images.githubusercontent.com/40337213/177483565-38c496b8-4dfb-4b14-a523-84796a025ca4.png)

- to change the threshold, open the slo/slo.yaml and modify the value : 
![image](https://user-images.githubusercontent.com/40337213/177486269-cd394cd1-e60e-4460-9707-211d9b6b306c.png)

Default value  :

	
	- target_threshold = 95 %  (10 % for SLO resources : CPU, memory)
	- timeframe = -1w (1 week for all SLOs)
	- warning_threshold = 98 % (20 % for SLO resources: CPU, memory)

- to change the performance threshold on the calculated service metric, open the calculated-metrics-service/calculated-metrics-service.yamlfile
![image](https://user-images.githubusercontent.com/40337213/177483773-08415f90-2394-49e1-b5ba-6d139717745c.png)

Default value :
	
	
	- performance-threshold = 500 ms  

This metric consumes DDU metric as a calculated service metric =>  https://www.dynatrace.com/support/help/shortlink/metric-cost-calculation

- to disable a slo from monaco, open slo/slo.yaml and comment the line: 
<img src="https://user-images.githubusercontent.com/40337213/176834195-e5676e9c-25bc-41e8-b094-87c9c053c1f1.png" width="600" height="200">

- how to find MZID:  

--> from the UI, the MZID is available in the URL : **Settings / Prefererences / Management Zones** 
![image](https://user-images.githubusercontent.com/40337213/177485757-5514048c-6c5c-4ec0-b44d-73cb0829cbda.png)

--> from the API 

	Managed : https://{your-domain}/e/{your-environment-id}/api/config/v1/managementZones&Api-Token=yyy
	Saas : https://{your-environment-id}.live.dynatrace.com/api/config/v1/managementZones&Api-Token=yyy
