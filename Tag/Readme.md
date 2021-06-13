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

      echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken
     
- backup your autotag config

      cd;cd quickstart-ace-configurator;
      ./monaco download -e=environments.yaml --downloadSpecificAPI auto-tag Backup

- deploy or update

      cd;cd quickstart-ace-configurator;
      ./monaco deploy -e=environments.yaml Tag/deploy-tag
      
- delete

      cd;cd quickstart-ace-configurator;
      ./monaco deploy -e=environments.yaml Tag/delete


- Result

![image](https://user-images.githubusercontent.com/40337213/121811414-a6abb980-cc64-11eb-81b5-d55cac8db561.png)

# Next Step

- [Naming](/Naming)

