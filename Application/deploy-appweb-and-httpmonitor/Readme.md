# Deploy web application with http monitor


You will create an application detection rule with a web application configuration based on the `DomainName` and an http monitor based on the same configuration name.  
This web application will be automatically named with that `app` - `DomainName` - `env`    
Add the Auto Tag with the 2 rules : 
 - Tag `app` : and catch the **app** in `app - DomainName - env`
 - Tag `env` : and catch the **env** in `app - DomainName - env`

By default the Session Replay : `ReplayPerc`= 10 %  
On prerequisite, you need to git clone this repository and install monaco [here](https://github.com/JLLormeau/OnDemand-Configuration-with-Monaco#ondemand-configuration-with-monaco)
 
- export variables

      export NEW_CLI=1
      export MyTenant=<MyTenant>
      export MyToken=<MyToken>
      export Tag_app=<app>
      export Tag_env=<env>
      export DomainName="www.monappli.com"
      export ReplayPerc=10
      
- test variables

      echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "Tag_app="$Tag_app;echo "Tag_env="$Tag_env;echo "DomainName="$DomainName;echo "ReplayPerc="$ReplayPerc
     
- deploy or update

      cd;cd quickstart-ace-configurator;
      ./monaco deploy -e=environments.yaml Application/deploy-appweb
      
- delete

      cd;cd quickstart-ace-configurator;
      echo " - \"application-web/"$Tag_app" - "$DomainName" - "$Tag_env"\"" >> Application/delete/delete.yaml;./monaco deploy -e=environments.yaml Application/delete;echo "delete:" > Application/delete/delete.yaml


# Result in Dynatrace 
- for this configuration  
       **Tag_app**=`easy`  
       **Tag_env**=`sandbox`  
   
   <img src="https://user-images.githubusercontent.com/40337213/119090024-59dd1600-ba0b-11eb-9cf0-2a9b54ef2725.png" width="500" height="200">
   <img src="https://user-images.githubusercontent.com/40337213/119090164-8db83b80-ba0b-11eb-9d31-9cb603b8feb1.png" width="500" height="600">


