# Deploy web application


You will create an application detection rule with a web application configuration base on the `DomainName`.  
This web application will be automatically named with that `app` - `DomainName` - `env`    
Add the Auto Tag with the 2 rules : 
 - Tag `app` : and catch the **app** in `app - DomainName - env`
 - Tag `env` : and catch the **env** in `app - DomainName - env`

By default the Session Replay : `ReplayPerc`= 10 %
On prerequisit, you need to git clone this repository and install monaco [here](https://github.com/JLLormeau/OnDemand-Configuration-with-Monaco#ondemand-configuration-with-monaco)
 
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
      echo " - \"Application/"$Tag_app" - $DomainName" - "$Tag_env"\"" >> Application/delete/delete.yaml;./monaco deploy -e=environments.yaml Application/delete;echo "delete:" > Application/delete/delete.yaml


# Result in Dynatrace 
- for this configuration  
       **Tag_app**=`easytravel03`  
       **Tag_env**=`sandbox`  
   
   <img src="https://user-images.githubusercontent.com/40337213/119018045-f23bb200-b99b-11eb-8e7c-ae5f55bc7518.png" width="600" height="700">

