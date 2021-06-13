# HostGroup

Before starting the **Quickstart Ace Configurator**, you have to define your **Host Group**. 
Based on our experience a host group has to contain, general role 

Recommanded informations :   

  - `_E_<env>` = environnement name (prod, or staging or dev etc...), prefer lower case for `<env>` 
  - `_T_<yes or no>` = Type of VM : dedicated to the application (`_T_yes`) or not (`_T_no`) 
  - `_A_<app>` = Application code (if existed) or application name (prefer short name), prefer lower case for `<app>`
 
Optionnel, depends on the context, you could have to add these informations :   
  
  - `_R_<role>`= the role of the VM in the application, prefer lower case for `<role>`
  - `_P_<project>`= for the project name, which contains many application, prefer lower case for `<project>`
  - `_D_<direction>`= the direction which contains many projects, prefer lower case for `<direction>`
  - `_Z_<zone>` = for the country, prefer lower case for `<zone>`
  - `_C_<company>`= for a hoster, prefer lower case for `<company>`
  - etc...

Constraints : 
  
   - No `_` and no `space`  in the name app, env, project,, role, zone, etc.
   - Prefer lower case for all name.

Example of HostGroup : 

  `_E_sandbox_A_easy_T_yes_P_lab-dynatrace`

Apply your HostGroup configuration at the manual installation  :

  ![image](https://user-images.githubusercontent.com/40337213/121800383-b3fb8080-cc31-11eb-9568-29d556ef30d7.png)
  
  `/bin/sh Dynatrace-OneAgent-Linux-1.217.162.sh --set-host-group=_E_sandbox_A_easy_T_yes_P_lab-dynatrace`

Modify the HostGroup configuration with OneAgent cli 

  `./oneagentctl --set-host-group="_E_sandbox_A_easy_T_yes_P_lab-dynatrace" --restart-service`
  
Generalizes this HostGroup configuration in your ansible roles : https://github.com/Dynatrace/Dynatrace-OneAgent-Ansible
 
 
# Next Step

- Create the [Tag](/Tag) with monaco :  
