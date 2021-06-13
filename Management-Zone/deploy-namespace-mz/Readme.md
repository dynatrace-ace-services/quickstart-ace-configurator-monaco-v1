# Deploy Management Zone for kubernetes

You will deploy management-zone with the name **[k8s] `NameSpace`.`Cluster`** for  a spcefic `ClusterName`

- export variables

      export NEW_CLI=1
      export MyTenant=<MyTenant>
      export MyToken=<MyToken>
      export NameSpace=<namespace>
      export Cluster=<clustername>

- test variables

      echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "NameSpace="$NameSpace;echo "Cluster="$Cluster
     
- backup your autotag config

      cd;cd quickstart-ace-configurator;
      ./monaco download -e=environments.yaml --downloadSpecificAPI management-zone Backup

- deploy or update

      cd;cd quickstart-ace-configurator;
      ./monaco deploy -e=environments.yaml Management-Zone/deploy-namespace-mz
      
- delete

      cd;cd quickstart-ace-configurator;
      echo " - \"management-zone/[k8s] "$NameSpace"."$Cluster"\"" >> Management-Zone/delete/delete.yaml;./monaco deploy -e=environments.yaml Management-Zone/delete;echo "delete:" > Tag/delete/delete.yaml


# Result in Dynatrace 
- create this management-zone :  
       **NameSpace**=`keptn`  
       **Cluster**=`microk8s`  
   
![image](https://user-images.githubusercontent.com/40337213/121814798-38222800-cc73-11eb-8fa0-2c9819006721.png)
