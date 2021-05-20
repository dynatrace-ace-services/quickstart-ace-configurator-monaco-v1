# Maintenance Window : OnceOnly

You will create a maintenance window for a specific period from `Start` to `Stop`
On prerequisit, you need to git clone this repository and install monaco [here](https://github.com/JLLormeau/OnDemand-Configuration-with-Monaco#ondemand-configuration-with-monaco)

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
      ./monaco deploy -e=environments.yaml Maintenance-Window/deploy-onceonly-mw
      
- stop

      cd;cd OnDemand-Configuration-with-Monaco;
      export Stop=`date +"%Y-%m-%d %H:%M"`;./monaco deploy -e=environments.yaml Maintenance-Window/deploy-onceonly-mw


- delete

      cd;cd OnDemand-Configuration-with-Monaco;
      echo " - \"maintenance-window/OnceOnly:"$Tag_app"_"$Tag_env"\"" >> Maintenance-Window/delete/delete.yaml;./monaco deploy -e=environments.yaml Maintenance-Window/delete;echo "delete:" > Maintenance-Window/delete/delete.yaml


# Result in Dynatrace 
- for this configuration  
       **Tag_app**=`easytravel03`  
       **Tag_env**=`sandbox`  
   
   <img src="https://user-images.githubusercontent.com/40337213/118992874-50a96600-b985-11eb-9daa-9f647b277d70.png" width="600" height="700">
