# Naming 

Base on the HostGroup recommandations, you will apply the rule naming for 
 - host
 - process group
 - service

- export variables

      export NEW_CLI=1
      export MyTenant=<MyTenant>
      export MyToken=<MyToken>
      
- test variables

      echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken
     
- deploy or update

      cd;cd quickstart-ace-configurator;
      ./monaco deploy -e=environments.yaml Naming/deploy-name
      
- delete

      cd;cd quickstart-ace-configurator;
      echo " - \"auto-tag/app\"" >> Tag/delete/delete.yaml;echo " - \"auto-tag/env\"" >> Tag/delete/delete.yaml;./monaco deploy -e=environments.yaml Tag/delete;echo "delete:" > Tag/delete/delete.yaml


- Result

![image](https://user-images.githubusercontent.com/40337213/119894270-b32dd380-bf3c-11eb-9aee-d11146792a88.png)
![image](https://user-images.githubusercontent.com/40337213/119894746-46ff9f80-bf3d-11eb-9c4d-c0c5f71b9ee5.png)

# Next Step

- [Naming](/Naming)

