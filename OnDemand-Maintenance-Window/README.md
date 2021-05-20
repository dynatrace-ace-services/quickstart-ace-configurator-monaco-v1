# Maintenance Window OnDemand

You will create a maintenance window for a specific period.
 
- export variables (date format `2021-05-21 23:59`)

      export NEW_CLI=1
      export MyTenant=<MyTenant>
      export MyToken=<MyToken>
      export Tag_app=<app>
      export Tag_env=<env>
      export start=`date +"%Y-%m-%d %H:%M"`
      export stop=`date +"%Y-%m-%d %H:%M" -d "+120 min"`
      
- test variables

      echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "app="$app;echo "env="$env;echo "start="$start;echo "stop="$stop
     
- deploy or update

      cd;cd OnDemand-Configuration-with-Monaco;
      ./monaco deploy -e=environments.yaml Maintenance_Window
      
- stop

      cd;cd test;
      export Stop=`date +"%Y-%m-%d %H:%M"`;./monaco deploy -e=environments.yaml Maintenance_Window


- delete

      cd;cd OnDemand-Configuration-with-Monaco;
      sed -i 's/app_env/'$app_$env'/g'  Maintenance_Window/DeleteOnDemandMaintenance//delete.yaml;./monaco deploy -e=environments.yaml   Maintenance_Window/DeleteOnDemandMaintenance/;sed -i 's/'$app_$env'/app_env/g' Maintenance_Window/DeleteOnDemandMaintenance//delete.yaml


