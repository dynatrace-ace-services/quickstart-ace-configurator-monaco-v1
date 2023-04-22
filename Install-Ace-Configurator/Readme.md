# Install the Ace Configurator

- git clone 
      
      cd;
      git clone https://github.com/dynatrace-ace-services/quickstart-ace-configurator

- install monaco v1 (deprecated)

      cd;cd quickstart-ace-configurator;
      curl -L https://github.com/dynatrace/dynatrace-configuration-as-code/releases/download/v1.8.9/monaco-linux-amd64 -o monaco
      chmod +x monaco;
      export NEW_CLI=1;
    
- create your token   
Go to your Dynatrace environment :  _Settings > Integration > Dynatrace API > Generate Token_   
Enable these privileges (more info about token permission for monaco [here](https://github.com/dynatrace-oss/dynatrace-monitoring-as-code#supported-configuration-types-and-token-permissions)):  
    <img src="https://user-images.githubusercontent.com/40337213/115966397-aed15d80-a52d-11eb-8156-a278b8f9a489.png" width="700" height="250">

       tip: keep the value of the token you will not be able to display it afterwards 

- export your Dynatrace environment variables for monaco 

      export MyTenant=abcd123.live.dynatrace.com (without https://...)
      export MyToken=xxxx1234yyyy1234

dynatrace saas tenant (and free trial) : "1234.live.dynatrace.com" (without https:// and / at the end of the line)  
dynatrace managed tenant : "1234.dynatrace-managed.com/e/abc123etc" (without https:// and / at the end of the line)  

- test variables

      echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;

# Backup your Dynatrace tenant configuration

- before starting, it's recommanded to backup your configuration  

      cd;cd quickstart-ace-configurator;
      ./monaco download -e=environments.yaml Backup

# Netx Step

- [Tag](/Tag)
