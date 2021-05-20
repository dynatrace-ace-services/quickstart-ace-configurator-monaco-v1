# Maintenance Window OnDemand

You will create a maintenance window for a specific period.
 
- export variables (date format `2021-05-21 23:59`)

      export NEW_CLI=1
      export MyTenant=<MyTenant>
      export MyToken=<MyToken>
      export Tag_app=<app>
      export Tag_env=<env>
      export Start=`date +"%Y-%m-%d %H:%M"`
      export Stop=`date +"%Y-%m-%d %H:%M" -d "+180 min"`
      
- test variables

      echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "Tag_app="$Tag_app;echo "Tag_env="$Tag_env;echo "Start="$Start;echo "Stop="$Stop
     
- deploy or update

      cd;cd OnDemand-Configuration-with-Monaco;
      ./monaco deploy -e=environments.yaml Maintenance-Window/deploy-ondemand-mw
      
- stop

      cd;cd OnDemand-Configuration-with-Monaco;
      export Stop=`date +"%Y-%m-%d %H:%M"`;./monaco deploy -e=environments.yaml Maintenance-Window/deploy-ondemand-mw


- delete

      cd;cd OnDemand-Configuration-with-Monaco;
      sed -i 's/app_env/'$app_$env'/g'  Maintenance-Window/delete-ondemand-mw/delete.yaml;./monaco deploy -e=environments.yaml   OMaintenance-Window/delete-ondemand-mw;sed -i 's/'$app_$env'/app_env/g' Maintenance-Window/delete-ondemand-mw/delete.yaml


