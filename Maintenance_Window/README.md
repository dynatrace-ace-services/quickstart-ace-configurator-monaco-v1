# Maintenance Window OnDemand

You will create a maintenance window for a specific period.

- git clone 
      
      cd;
      git clone https://github.com/JLLormeau/test

- install monaco

      cd;cd test;
      wget https://github.com/dynatrace-oss/dynatrace-monitoring-as-code/releases/download/v1.5.3/monaco-linux-amd64;
      mv monaco-linux-amd64 monaco;
      chmod +x monaco;
    
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

      cd;cd test;
      ./monaco deploy -e=environments.yaml OnDemandMaintenance


- stop

      cd;cd test;
      export Stop=`date +"%Y-%m-%d %H:%M"`;./monaco deploy -e=environments.yaml OnDemandMaintenance


- delete

      cd;cd test;
      sed -i 's/CodeAppli/'$CodeAppli'/g' DeleteMaintenance/delete.yaml;./monaco deploy -e=environments.yaml DeleteMaintenance;sed -i 's/'$CodeAppli'/CodeAppli/g' DeleteMaintenance/delete.yaml


