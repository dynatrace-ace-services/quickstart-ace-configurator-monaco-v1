# Maintenance window

- install monaco

      cd;cd test;
      wget https://github.com/dynatrace-oss/dynatrace-monitoring-as-code/releases/download/v1.5.2/monaco-linux-amd64;
      mv monaco-linux-amd64 monaco;
      chmod +x monaco;
      export NEW_CLI=1;
      ./monaco --version


- test variable

      echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "CodeAppli="$CodeAppli;echo "CodeAppliUpper="$CodeAppliUpper;echo "Start="$Start;echo "Stop="$Stop
     
- deploy
 
      cd;cd test; 
      ./monaco deploy -e=environments.yaml OnDemandMaintenance

- delete

      cd;cd test;
      sed -i 's/CodeAppli/'$CodeAppli'/g' DeleteMaintenance/delete.yml;./monaco deploy -e=environments.yaml DeleteMaintenance;sed -i 's/'$CodeAppli'/CodeAppli/g' DeleteMaintenance/delete.yaml
