# On demand configuration with Monaco

You will create generic configurations in your Dynatrace environement with monaco for :   
      - [Maintenance window](/Maintenance-Window)  
      - [Application](/Application)  
      - [Management-Zone](/Application)  

By default, this prebuild configuration with monaco has been designed to be filtred by these 2 tags `app` and tag `env` 
   - `app` to define your application : easytravel, socshop, monsterticket etc.  
   - `env` to define your environment : prod, staging, dev etc. 
    
Create these 2 tags `app` and `env` and apply them to all your entities (host, process groups, services, application, http monitor, browser monitor, custom etc...)  
    <img src="https://user-images.githubusercontent.com/40337213/119023814-af310d00-b9a2-11eb-8fe8-e83b6b53fc4e.png" width="600" height="200">


# Install this prebuild configuration

- git clone 
      
      cd;
      git clone https://github.com/JLLormeau/OnDemand-Configuration-with-Monaco

- install monaco

      cd;cd OnDemand-Configuration-with-Monaco;
      wget https://github.com/dynatrace-oss/dynatrace-monitoring-as-code/releases/latest/download/monaco-linux-amd64;
      mv monaco-linux-amd64 monaco;
      chmod +x monaco;
    
- create your token   
Go to your Dynatrace environment :  _Settings > Integration > Dynatrace API > Generate Token_   
Enable these privileges (more info about token permission for monaco [here](https://github.com/dynatrace-oss/dynatrace-monitoring-as-code#supported-configuration-types-and-token-permissions)):  
    <img src="https://user-images.githubusercontent.com/40337213/115966397-aed15d80-a52d-11eb-8156-a278b8f9a489.png" width="700" height="250">

       tip: keep the value of the token you will not be able to display it afterwards 

-  export your Dynatrace environment variables for monaco 

       export MyTenant=abcd123.live.dynatrace.com (without https://...)
       export MyToken=xxxx1234yyyy1234


Now, you can apply this prebuid configuration for these use cases :    

      - [Deploy your Maintenance window  per `app` and `env`](/Maintenance-Window)  
      - [Deploy your Application and Synthetic configuration per `app` and `env`](/Application)  
      - [Deploy your Management-Zone and Alerting profile  per `app` and `env`](/Application)  

