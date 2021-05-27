# Deploy web application with bowser monitor


You will create an application detection rule with a web application configuration based on the `DomainName` and an http monitor based on the same configuration name.  
This web application will be automatically named with that `app`.`env` - `DomainName`     
Add the Auto Tag with the 2 rules for application-web and browser-monitor : 
 - Tag `app` : and catch the **app** in `app.env - DomainName` 
 - Tag `env` : and catch the **env** in `app.env - DomainName`

By default the Session Replay : `ReplayPerc`= 10 %  
On prerequisite, you need to git clone this repository and install monaco [here](https://github.com/dynatrace-ace-services/quickstart-ace-configurator#install-the-quickstart-ace-configurator)
 
- export variables

      export NEW_CLI=1
      export MyTenant=<MyTenant>
      export MyToken=<MyToken>
      export Tag_app=<app>
      export Tag_env=<env>
      export DomainName="www.monappli.com"
      export ReplayPerc=10
      export EnableSynthetic=true
      
- test variables

      echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "Tag_app="$Tag_app;echo "Tag_env="$Tag_env;echo "DomainName="$DomainName;echo "ReplayPerc="$ReplayPerc"%";echo "EnableSynthetic="$EnableSynthetic
     
- deploy or update

      cd;cd quickstart-ace-configurator;
      ./monaco deploy -e=environments.yaml Application/deploy-appweb-and-browsermonitor

      
- delete

      cd;cd quickstart-ace-configurator;
      echo " - \"application-web/"$Tag_app" - "$DomainName" - "$Tag_env"\"" >> Application/delete/delete.yaml;echo " - \"synthetic-monitor/"$Tag_app" - "$DomainName" - "$Tag_env"\"" >> Application/delete/delete.yaml;./monaco deploy -e=environments.yaml Application/delete;echo "delete:" > Application/delete/delete.yaml


# Result in Dynatrace 
- for this configuration  
       **Tag_'app'**=`easy`  
       **Tag_'env'**=`sandbox`  
   
   <img src="https://user-images.githubusercontent.com/40337213/119090024-59dd1600-ba0b-11eb-9cf0-2a9b54ef2725.png" width="500" height="200">
   <img src="https://user-images.githubusercontent.com/40337213/119092702-08368a80-ba0f-11eb-8bd8-ccc311c7e9ee.png" width="1000" height="600">


