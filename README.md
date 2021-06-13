# QuickStart : Getting Started with the Ace Configurator 

Recommandations, define your hostgroup with this best practice :  
      - [HostGroup](/HostGroup)  

Moncao installation and backup configuration :  
      - [install-ace-configurator](/Install-Ace-Configurator)
      
You will create generic configurations in your Dynatrace environement with Monaco for :   
      - [Tag](/Tag)  
      - [Management-Zone](/Management-Zone)  
      - [Application](/Application)  
      - [Maintenance window](/Maintenance-Window)  


By default, this prebuild configuration with monaco has been designed to be filtred by these 2 tags `app` and tag `env` 
   - `app` to define your application : easytravel, socshop, monsterticket etc.  
   - `env` to define your environment : prod, staging, dev etc. 
Use the HostGroup recommandations defined above. 
    
The quickstart ace configurator presents the best practice to start the deployment of the OneAgent with the best configuration.  
Monaco is used to apply the generic configuration based on the 2 main tags `app` and `env` and used them for all the entities (host, process groups, services, application, http monitor, browser monitor, custom etc...)  

## If you start from scratch 

Use the [HostGroup](/HostGroup) recommandations and deploy the genecir [Tag](/Tag) definition with monaco.  
    - [HostGroup](/HostGroup)
    - [Tag](/Tag) 
    
After you can apply these configurations on your context as many times as necessary : 
    - [Management-Zone](/Management-Zone)  
    - [Application](/Application)  
    - [Maintenance window](/Maintenance-Window)  

## If you start with your own HostGroup configuration 

In this case import the [Tag](/Tag) and adapt them to your context : 
    - [Tag](/Tag) + apply your own configuration

Once all your entities have the 2 tags `app` and `env` like describe in result, you can apply these configurations on your context as many times as necessary :  
   - [Deploy your Management-Zone and Alerting profile  per `app` and `env`](/Management-Zone)  
   - [Deploy your Application and Synthetic configuration per `app` and `env`](/Application)  
   - [Deploy your Maintenance window  per `app` and `env`](/Maintenance-Window)  


## Result

We will use these 2 tags `app` and `env` as the base of all the configuration :    
 <img src="https://user-images.githubusercontent.com/40337213/119023814-af310d00-b9a2-11eb-8fe8-e83b6b53fc4e.png" width="600" height="200">
 <img src="https://user-images.githubusercontent.com/40337213/119873392-c8970380-bf24-11eb-9716-acf50d1cbe09.png" width="300" height="200">


# Fisrt Step

- [install-ace-configurator](/Install-Ace-Configurator)

