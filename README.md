# Foundations for deployment and configuration

✅ Deployment best practices : https://github.com/dynatrace-ace-services/quickstart-ace-configurator#readme  
Easy ITSM integration : https://github.com/dynatrace-ace-services/easy-itsm-integration#readme  
SLO Simply Smarter installation : https://github.com/dynatrace-ace-services/slo-simply-smarter#readme  

Youtube  : [From zero to hero in 2 minutes](https://youtu.be/vyabfN9zt8c)  
Youtube  : [Full demo - From zero to hero](https://youtu.be/irxN7PJd43M)  
Youtube : [SLO for OPS - Boost your Service Desk integration](https://youtu.be/ugauVEjtfWo)  
Monaco introduction : [What is Monaco for Dynatrace?](/What-is-Monaco-for-Dynatrace.pdf)  
BizOpsConfigurator: [Welcome to Dynatrace BizOps Dashboards](https://dynatrace.github.io/BizOpsConfigurator/index.html#prerequisites)  

![image](https://user-images.githubusercontent.com/40337213/216826127-38c717f5-6a4c-4883-be86-8fda9d9db49c.png)

## Best practices & configurations
In this QuickStart Ace Configurator you will do : 

1) Define the hostgroup with these best practices based on our experience:    
      - [HostGroup](/HostGroup)  

2) Install Monaco and backup your Dynatrace tenant configuration before starting :  
      - [Install-Ace-Configurator](/Install-Ace-Configurator)

3) Create generic configurations in your Dynatrace environment with Monaco for :   
      - [Tag](/Tag)  
      - [Naming](/Naming) 
      - [Management-Zone](/Management-Zone)
      - [Application](/Application)  
      - [Maintenance window](/Maintenance-Window) 
      - [SLO per MZ application centric](/SLO)  

## If you start from scratch 

Use the [HostGroup](/HostGroup) recommandations and deploy the genecir [Tag](/Tag) definition with monaco.   
    - [HostGroup](/HostGroup)  
    - [Tag](/Tag)  
    - [Naming](/Naming) (based on HostGroup recommandations) 
    
After you can apply these configurations on your context as many times as necessary :  
    - [Management-Zone](/Management-Zone)  
    - [Application](/Application)  
    - [Maintenance window](/Maintenance-Window)  

## If you start with your own HostGroup configuration 

In this case import the [Tag](/Tag) and adapt them to your context :   
    - [Tag](/Tag)  
    - Modify tag rule to apply your own configuration to `app` and `env` auto tag  
    - Do your own naming for host, process group and service  

Once all your entities have the 2 tags `app` and `env` like describe in result, you can apply these configurations on your context as many times as necessary :  
    - [Deploy your Management-Zone and Alerting profile  per `app` and `env`](/Management-Zone)  
    - [Deploy your Application and Synthetic configuration per `app` and `env`](/Application)  
    - [Deploy your Maintenance window  per `app` and `env`](/Maintenance-Window)  


## Result

By default, this prebuild configuration with monaco has been designed to be filtred by these 2 tags `app` and tag `env` 
   - `app` to define your application : easytravel, socshop, monsterticket etc.  
   - `env` to define your environment : prod, staging, dev etc. 
Use the HostGroup recommandations defined above. 
 <img src="https://user-images.githubusercontent.com/40337213/119023814-af310d00-b9a2-11eb-8fe8-e83b6b53fc4e.png" width="600" height="200">
    
The quickstart ace configurator presents the best practice to start the deployment of the OneAgent with this generic configuration.  
Monaco is used to apply the generic configuration based on the 2 main tags `app` and `env` and used them for all the entities (host, process groups, services, application, http monitor, browser monitor, custom etc...)  
 <img src="https://user-images.githubusercontent.com/40337213/119873392-c8970380-bf24-11eb-9716-acf50d1cbe09.png" width="300" height="200">


# Next Step

 - [HostGroup](/HostGroup)  


