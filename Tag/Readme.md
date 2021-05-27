# Deploy autotag


You will create these 2 autotags :  
 - `app`
 - `env`

Adjust these autotags to adapt your context : 
These 2 autotags are already configure for [Application and Syntetic](https://github.com/dynatrace-ace-services/quickstart-ace-configurator/tree/main/Application) setcion 

**Warning** If you already have autotag with name `app` or `env` you will erase your autoag. 


- export variables

      export NEW_CLI=1
      export MyTenant=<MyTenant>
      export MyToken=<MyToken>
      
- test variables

      echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "
     
- backup your autotag config

      cd;cd quickstart-ace-configurator;
      ./monaco download -e=environments.yaml --auto-tag Backup

- deploy or update

      cd;cd quickstart-ace-configurator;
      ./monaco deploy -e=environments.yaml Tag
      
- delete

      cd;cd quickstart-ace-configurator;
      echo " - \"auto-tag/app\"" >> Application/delete/delete.yaml;echo " - \"auto-tag/env\"";./monaco deploy -e=environments.yaml Tag/delete;echo "delete:" > Tag/delete/delete.yaml


# Result in Dynatrace 
- create these autotags :  
       **Tag_app**=`easy`  
       **Tag_env**=`sandbox`  
   
![image](https://user-images.githubusercontent.com/40337213/119894270-b32dd380-bf3c-11eb-9aee-d11146792a88.png)
![image](https://user-images.githubusercontent.com/40337213/119894746-46ff9f80-bf3d-11eb-9c4d-c0c5f71b9ee5.png)
