# Deploy Management Zone for Legacy SI


You will deploy management-zone with the name `app`.`env` for all the entities which have these 2 tags :  
 - **Tag_app** = `app`
 - **Tag_env** = `env`


- export variables

      export NEW_CLI=1
      export MyTenant=<MyTenant>
      export MyToken=<MyToken>
      export Tag_app=<app>
	  export Tag_env=<env>

- test variables

      echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "Tag_app="$Tag_app;echo "Tag_env="$Tag_env
     
- backup your autotag config

      cd;cd quickstart-ace-configurator;
      ./monaco download -e=environments.yaml --downloadSpecificAPI management-zone Backup

- deploy or update

      cd;cd quickstart-ace-configurator;
      ./monaco deploy -e=environments.yaml Management-Zone/deploy-legacy-mz
      
- delete

      cd;cd quickstart-ace-configurator;
      echo " - \"management-zone/"$Tag_app"."$Tag_env"\"" >> Management-Zone/delete/delete.yaml;./monaco deploy -e=environments.yaml Management-Zone/delete;echo "delete:" > Tag/delete/delete.yaml


# Result in Dynatrace 
- create this management-zone :  
       **Tag_app**=`easy`  
       **Tag_env**=`sandbox`  
   
![image](https://user-images.githubusercontent.com/40337213/119894270-b32dd380-bf3c-11eb-9aee-d11146792a88.png)
![image](https://user-images.githubusercontent.com/40337213/119894746-46ff9f80-bf3d-11eb-9c4d-c0c5f71b9ee5.png)
