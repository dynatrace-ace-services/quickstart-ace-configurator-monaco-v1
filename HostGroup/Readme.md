# Host_Group

Before starting the **Quickstart Ace Configurator**, you have to define your **Host Group**. 
Based on our experience a host group has to contain "application name" and "environment"  

## Basic approach  

- `host_group` = `<app>_<env>`
- `tag` = host_group for all entities (host, process group, service, custom device, application ...)
- `management_zone` based on host_group tag.

in case you need to deal with others information: for example = Business Unit , Region , Tier , Customer name  
you can add this information in metadata.   

![image](https://user-images.githubusercontent.com/40337213/225312399-fed466ca-ab10-405a-ac4b-21f7a5f1a85a.png)

Avantage of the basic approach :
- the tag and mz rules are simple to do.
- no regex.


## Advanced approach  

You can use this approach to be completly generic. 
- All information are defined in the host_group. 
- Need tag with regex. 

Recommanded informations :   

  - `_E_<env>` = environnement name (prod, or staging or dev etc...), prefer lower case for `<env>` 
  - `_M_<yes or no>` = is the VM mutualized ? (`_M_yes`) or (`_M_no`) 
  - `_A_<app>` = Application code (if existed) or application name (prefer short name), prefer lower case for `<app>`  
  These 3 field must be filled. Apply _A_`empty` or _E_`empty` in case your are no value to put.
 
Optionnal, depends on the context, you could have to add these informations :   
  
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

  `_E_sandbox_A_easy_M_no_P_lab-dynatrace`

Apply your HostGroup configuration at the manual installation  :

 ![image](https://user-images.githubusercontent.com/40337213/130984116-0d33e833-51d0-4499-b0c4-489633ef2e86.png)
  
  `/bin/sh Dynatrace-OneAgent-Linux-1.217.162.sh --set-host-group=_E_sandbox_A_easy_M_no_P_lab-dynatrace`

Modify the HostGroup configuration with OneAgent cli 

  `./oneagentctl --set-host-group="_E_sandbox_A_easy_M_no_P_lab-dynatrace" --restart-service`
  
Generalizes this HostGroup configuration in your ansible roles : https://github.com/Dynatrace/Dynatrace-OneAgent-Ansible
 
 
# Next Step

- [Install-Ace-Configurator](/Install-Ace-Configurator)
