# Maintenance Window : Bank Holidays France

This monaco template generates the maintenance window to disbale notification for all web applications in case of traffic drop 
![image](https://user-images.githubusercontent.com/40337213/206111851-c4bdd8a7-b31e-4b1b-87ae-c974879199c0.png)

This alert is triggered if "today" has less activity than Day-7.   
In case "today" is a bank holiday, you need this monaco template to disable notification.

- export variables (date format `mm-dd`)

      export NEW_CLI=1
      export MyTenant=<MyTenant>
      export MyToken=<MyToken>
      
      export An=2023
      export Lundi-paques=04-10
      export Lundi-pentecote=05-28
      expotr Ascension=05-18

      
- test variables

      echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "AN="$AN;echo "Lundi-paques="$Lundi-paques;echo "Lundi-pentecote="$Lundi-pentecote;echo "Ascension="$Ascension
     
- deploy or update

      cd;cd quickstart-ace-configurator;
      ./monaco deploy -e=environments.yaml Maintenance-Window/bank-holidays-france
      
