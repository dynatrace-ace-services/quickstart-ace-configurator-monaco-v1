# Deploy SLO for Management Zone

Export the variable:

	 export MZ=[MZ-name]

Deploy the configuration:

	cd;cd quickstart-ace-configurator;
	./monaco deploy -e=environments.yaml SLO/deploy-step1
	./monaco deploy -e=environments.yaml SLO/deploy-step2

Default configuration:

![image](https://user-images.githubusercontent.com/40337213/176833940-9d27f92e-eb72-49c6-87ed-72b84eca55bb.png)

- to disable a slo from monaco, open slo/slo.yaml and comment the line: 
![image](https://user-images.githubusercontent.com/40337213/176834195-e5676e9c-25bc-41e8-b094-87c9c053c1f1.png)

- to chnage the threshold, open the slo/xxx.json and modify the value : 
![image](https://user-images.githubusercontent.com/40337213/176834354-fb68c020-7b7c-4a83-b518-92736ddaac9a.png)


Dashboard :
 import **Dynatrace_Simple Smarter** to have slo dashboard for management zone centric view :
 	https://dynatrace.github.io/BizOpsConfigurator/index.html#downloadExcel

Dynatrace_Simply Smarter home page
![image](https://user-images.githubusercontent.com/40337213/176837340-187a05bb-ef54-401a-92d2-77f15eadc503.png)


![image](https://user-images.githubusercontent.com/40337213/176836841-76a461e0-3d9f-4bd3-adaf-840ad679e44b.png)
	

