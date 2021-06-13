# Deploy web application


You will create an application detection rule with a web application configuration based on the `DomainName`.  
This web application will be automatically named with that [`app`.`env`] `DomainName`  
As the appliation name is limited use `ShortName` if `DomaineName` is too long.  
Add the [AutoTag](/Tag) with the 2 rules : 
 - Tag `app` : and catch the **app** in `[app.env] DomainName` 
 - Tag `env` : and catch the **env** in `[app.env] DomainName`

By default the Session Replay : `ReplayPerc`= 10 %  
On prerequisite, you need to git clone this repository and install monaco [here](https://github.com/JLLormeau/OnDemand-Configuration-with-Monaco#ondemand-configuration-with-monaco)
 
- export variables

      export NEW_CLI=1
      export MyTenant=<MyTenant>
      export MyToken=<MyToken>
      export Tag_app=<app>
      export Tag_env=<env>
      export DomainName="www.monappli.com"
      export ShortName=$DomainName
      export ReplayPerc=10
      
- test variables

      echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "Tag_app="$Tag_app;echo "Tag_env="$Tag_env;echo "DomainName="$DomainName;echo "ShortName="$ShortName;echo "ReplayPerc="$ReplayPerc
     
- deploy or update

      cd;cd quickstart-ace-configurator;
      ./monaco deploy -e=environments.yaml Application/deploy-appweb
      
- delete

      cd;cd quickstart-ace-configurator;
      echo " - \"application-web/["$Tag_app"."$Tag_env"] "$ShortName"\"" >> Application/delete/delete.yaml;./monaco deploy -e=environments.yaml Application/delete;echo "delete:" > Application/delete/delete.yaml


# Result in Dynatrace 
- for this configuration  
       **Tag_app**=`easy`  
       **Tag_env**=`sandbox`  
   
   ![image](https://user-images.githubusercontent.com/40337213/119887862-f71cda80-bf34-11eb-8ea2-47af768c0118.png)
    ![image](https://user-images.githubusercontent.com/40337213/119887790-dfdded00-bf34-11eb-9199-7dc600c0759e.png)
