# Maintenance Window : Daily

You will create a daily maintenance window which will be actif every day at the same period starts at `DailyStart` wt the same period which starts at `DailyStart` and with the duration `DurationMinutes`.     
This maintenance window  will be enabled during `Star` to `End` period.  
This daily maintenance window is applied to the entities filtered by these 2 tags `app` and `env`    
On prerequisit, you need to git clone this repository and install monaco [here](./OnDemand-Configuration-with-Monaco#install-this-prebuild-configuration)
 
- export variables

      export NEW_CLI=1
      export MyTenant=<MyTenant>
      export MyToken=<MyToken>
      export Tag_app=<app>
      export Tag_env=<env>
      export DailyStart="19:00"
      export DurationMinutes="720"
      export Start=`date +"%Y-%m-%d %H:%M"`
      export End=`date +"%Y-%m-%d %H:%M" -d "+10 year"`
      
- test variables

      echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "Tag_app="$Tag_app;echo "Tag_env="$Tag_env;echo "DailyStart="$DailyStart;echo "DurationMinutes="$DurationMinutes;echo "Start="$Start;echo "End="$End
     
- deploy or update

      cd;cd OnDemand-Configuration-with-Monaco;
      ./monaco deploy -e=environments.yaml Maintenance-Window/deploy-daily-mw
      
- delete

      cd;cd OnDemand-Configuration-with-Monaco;
      echo " - \"maintenance-window/Daily:"$Tag_app"_"$Tag_env"\"" >> Maintenance-Window/delete/delete.yaml;./monaco deploy -e=environments.yaml Maintenance-Window/delete;echo "delete:" > Maintenance-Window/delete/delete.yaml


# Result in Dynatrace 
- for this configuration  
       **Tag_app**=`easytravel03`  
       **Tag_env**=`sandbox`  
   
   <img src="https://user-images.githubusercontent.com/40337213/119017255-1b0f7780-b99b-11eb-91ef-0011f5161ba0.png" width="600" height="700">

