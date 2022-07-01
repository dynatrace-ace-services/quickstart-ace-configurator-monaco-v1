# SLO for Management Zone
![image](https://user-images.githubusercontent.com/40337213/176840719-f5963a4e-7fd4-4a98-98e7-45a7d85eaf0e.png)

## Prerequisite
- [Install-Ace-Configurator](/Install-Ace-Configurator)
	
## Export the variable:

	 export MZ=[MZ-name]

## Deploy the configuration:

	cd;cd quickstart-ace-configurator;
	./monaco deploy -e=environments.yaml SLO/deploy-step1
	./monaco deploy -e=environments.yaml SLO/deploy-step2


## Dashboard :
 import **Dynatrace_Simple Smarter** to have slo dashboard for management zone centric view :
 	https://dynatrace.github.io/BizOpsConfigurator/index.html#downloadExcel

Dynatrace_Simply Smarter home page
![image](https://user-images.githubusercontent.com/40337213/176837340-187a05bb-ef54-401a-92d2-77f15eadc503.png)

SLO management zone centric
![image](https://user-images.githubusercontent.com/40337213/176838706-36f87d7d-485f-4e03-a01e-cf80c40278a6.png)

Analyze view
![image](https://user-images.githubusercontent.com/40337213/176836841-76a461e0-3d9f-4bd3-adaf-840ad679e44b.png)
	

## Default configuration:  
<img src="https://user-images.githubusercontent.com/40337213/176833940-9d27f92e-eb72-49c6-87ed-72b84eca55bb.png" width="600" height="200">

- to disable a slo from monaco, open slo/slo.yaml and comment the line: 
<img src="https://user-images.githubusercontent.com/40337213/176834195-e5676e9c-25bc-41e8-b094-87c9c053c1f1.png" width="600" height="200">

- to change the threshold, open the slo/xxx.json and modify the value : 
![image](https://user-images.githubusercontent.com/40337213/176834354-fb68c020-7b7c-4a83-b518-92736ddaac9a.png)
