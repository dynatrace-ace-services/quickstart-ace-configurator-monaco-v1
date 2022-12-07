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
      export Lundi_paques=04-10
      export Lundi_pentecote=05-28
      export Ascension=05-18

      
- test variables

      echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "AN="$AN;echo "Lundi_paques="$Lundi_paques;echo "Lundi_pentecote="$Lundi_pentecote;echo "Ascension="$Ascension
     
- deploy or update

      cd;cd quickstart-ace-configurator;
      ./monaco deploy -e=environments.yaml Maintenance-Window/template-bank-holidays-france
      
![image](https://user-images.githubusercontent.com/40337213/206142986-ea41db02-a8c9-48d3-90fd-da21a96b22c1.png)
