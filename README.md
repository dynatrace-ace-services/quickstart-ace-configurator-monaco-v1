# On demand configuration with Monaco

You will create generic configuration with monaco for :   
      - [Maintenance window](/Maintenance-Window)  
      - [Application](/Application)  
      - [Management-Zone](/Application)  

By default, these configurations are filtered by application (with tag `app`) and by environemnt (with tag `env`)
Apply these 2 tags to all your entities (host, process groups, services, application, http monitor, browser monitor, custom etc...)
If you have organized your Autotag with these 2 tags like that, you can directly use these prebuild configurations with monaco:  
   <img src="https://user-images.githubusercontent.com/40337213/119023814-af310d00-b9a2-11eb-8fe8-e83b6b53fc4e.png" width="600" height="200">


# Prerequisite

1) git clone 
      
      cd;
      git clone https://github.com/JLLormeau/OnDemand-Configuration-with-Monaco

1) install monaco

      cd;cd OnDemand-Configuration-with-Monaco;
      wget https://github.com/dynatrace-oss/dynatrace-monitoring-as-code/releases/latest/download/monaco-linux-amd64;
      mv monaco-linux-amd64 monaco;
      chmod +x monaco;
    
1) create your token   
Go to your Dynatrace environment :  _Settings > Integration > Dynatrace API > Generate Token_   
Enable these privileges (more info about token permission for monaco [here](https://github.com/dynatrace-oss/dynatrace-monitoring-as-code#supported-configuration-types-and-token-permissions)):  
    <img src="https://user-images.githubusercontent.com/40337213/115966397-aed15d80-a52d-11eb-8156-a278b8f9a489.png" width="700" height="250">

       tip: keep the value of the token you will not be able to display it afterwards 

1) export your Dynatrace environment variables for monaco 

       export MyTenant=abcd123.live.dynatrace.com (without https://...)
       export MyToken=xxxx1234yyyy1234
