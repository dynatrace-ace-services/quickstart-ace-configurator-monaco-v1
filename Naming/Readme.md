# Naming 

Base on the HostGroup recommandations, you will apply the rule naming for **host**, **process group** and **service**

- export variables

      export NEW_CLI=1
      export MyTenant=<MyTenant>
      export MyToken=<MyToken>
      
- test variables

      echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken
     
- deploy or update

      cd;cd quickstart-ace-configurator;
      ./monaco deploy -e=environments.yaml Naming/deploy-naming-rules
      
- delete

      cd;cd quickstart-ace-configurator;
      echo " - \"auto-tag/app\"" >> Tag/delete/delete.yaml;echo " - \"auto-tag/env\"" >> Tag/delete/delete.yaml;./monaco deploy -e=environments.yaml Tag/delete;echo "delete:" > Tag/delete/delete.yaml


- Result
![image](https://user-images.githubusercontent.com/40337213/121803578-a0a4e100-cc42-11eb-85e5-319253a0b63b.png)


# Next Step

- [Naming](/Naming)

