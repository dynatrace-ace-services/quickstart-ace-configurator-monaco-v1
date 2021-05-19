# Maintenance Window OnDemand

You will create a maintenance window for a specific period.
 
- export variables (date format `2021-05-21 23:59`)

      export NEW_CLI=1
      export MyTenant=<MyTenant>
      export MyToken=<MyToken>
      export CodeAppli=<CodeAppli>
      export CodeAppliUpper=`echo $CodeAppli|tr [:lower:] [:upper:]`
      export Start=`date +"%Y-%m-%d %H:%M"`
      export Stop=`date +"%Y-%m-%d %H:%M" -d "+120 min"`
      
- test variables

      echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "CodeAppli="$CodeAppli;echo "CodeAppliUpper="$CodeAppliUpper;echo "Start="$Start;echo "Stop="$Stop
     
- deploy or update

      cd;cd OnDemand-Configuration-with-Monaco;
      ./monaco deploy -e=environments.yaml OnDemand-Configuration-with-Monaco/Maintenance_Window
      
- stop

      cd;cd test;
      export Stop=`date +"%Y-%m-%d %H:%M"`;./monaco deploy -e=environments.yaml OnDemand-Configuration-with-Monaco/Maintenance_Window


- delete

      cd;cd OnDemand-Configuration-with-Monaco;
      sed -i 's/app_env/'$app_$env'/g'  OnDemand-Configuration-with-Monaco/MeleteMaintenance/delete.yaml;./monaco deploy -e=environments.yaml  OnDemand-Configuration-with-Monaco/DeleteMaintenance;sed -i 's/'$app_$env'/app_env/g' OnDemand-Configuration-with-Monaco/DeleteMaintenance/delete.yaml


