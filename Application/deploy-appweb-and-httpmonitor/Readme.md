# Deploy web application with http monitor


You will create an application detection rule with a web application configuration based on the `DomainName` and an http monitor based on the same configuration name.  
This web application will be automatically named with that [`app`.`env`] `DomainName`   
As the appliation name is limited use `ShortName` if `DomaineName` is too long.  
Add the [AutoTag](/Tag) with the 2 rules for application-web and http-monitor : 
 - Tag `app` : and catch the **app** in `[app.env] DomainName` 
 - Tag `env` : and catch the **env** in `[app.env] DomainName`

Default configuration for http monitor : Public Location = `Paris` and `Marseille` and Frequence = 5 min.
Default configuration for application Session Replay : `ReplayPerc`= 10 %. 
 
- export variables

      export NEW_CLI=1
      export MyTenant=<MyTenant>
      export MyToken=<MyToken>
      export Tag_app=<app>
      export Tag_env=<env>
      export Protocol="https"
      export DomainName="www.monappli.com"
      export ShortName=$DomainName
      export ReplayPerc=10
      export EnableSynthetic=true
      
- test variables

      echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "Tag_app="$Tag_app;echo "Tag_env="$Tag_env;echo "Protocol="$Protocol;echo "DomainName="$DomainName;echo "ShortName="$ShortName;echo "ReplayPerc="$ReplayPerc;echo "EnableSynthetic="$EnableSynthetic
     
- deploy or update

      cd;cd quickstart-ace-configurator;
      ./monaco deploy -e=environments.yaml Application/deploy-appweb-and-httpmonitor

      
- delete

      cd;cd quickstart-ace-configurator;
      echo " - \"application-web/["$Tag_app"."$Tag_env"] "$ShortName"\"" >> Application/delete/delete.yaml;echo " - \"synthetic-monitor["$Tag_app"."$Tag_env"] "$ShortName"\"" >> Application/delete/delete.yaml;./monaco deploy -e=environments.yaml Application/delete;echo "delete:" > Application/delete/delete.yaml


# Result in Dynatrace 
- for this configuration  
       **Tag_app**=`easy`  
       **Tag_env**=`sandbox`  
       **ShortName**=`dynatracelab01`  
       **DomaineName**=`dynatracelab01.francecentral.cloudapp.azure.com`   
       **Protocol**=`http`  
       **EnableSynthetic**=`true`  
   
 ![image](https://user-images.githubusercontent.com/40337213/121808239-cf798200-cc57-11eb-8a6d-37b460bdc700.png)
