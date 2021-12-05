# 00-install-Monaco
           
1) download the lab  
Copy the command with the copy button in the left corner.  
Paste the command on you VM.  

       cd;
       git clone https://github.com/dynatrace-ace-services/easy-dynatrace-with-monaco.git

2) download monaco (monaco-linux-amd64 -more distrib [here](https://github.com/dynatrace-oss/dynatrace-monitoring-as-code/releases/))  

       cd;cd easy-dynatrace-with-monaco;
       wget https://github.com/dynatrace-oss/dynatrace-monitoring-as-code/releases/latest/download/monaco-linux-amd64;
       mv monaco-linux-amd64 monaco;
       chmod +x monaco

3) new version NEW_CLI=1   
In this lab we will use only the new cli version of monaco.  
click [here](https://github.com/dynatrace-oss/dynatrace-monitoring-as-code#experimental-new-cli) for documentation   

       export NEW_CLI=1;
       cd;cd easy-dynatrace-with-monaco;
       ./monaco --version

- expected result 
![image](https://user-images.githubusercontent.com/40337213/116585744-fdf60480-a918-11eb-891a-8ee23dc1a5fb.png)

- to have more help 

      cd;cd easy-dynatrace-with-monaco;
      ./monaco -h

  ![image](https://user-images.githubusercontent.com/40337213/116579510-bd938800-a912-11eb-9ee9-ef5b32583d59.png)

4) create your token   
Go to your Dynatrace environment :  _Settings > Integration > Dynatrace API > Generate Token_   
with these privileges (more info about token permission for monaco [here](https://github.com/dynatrace-oss/dynatrace-monitoring-as-code#supported-configuration-types-and-token-permissions):  
    <img src="https://user-images.githubusercontent.com/40337213/115959740-ffd15980-a50d-11eb-8f03-9bffeb0b1141.png" width="450" height="250">

       tip: keep the value of the token you will not be able to display it afterwards 

5) the environment.yaml contains the configuration of your dynatrace tenants     
    <img src="https://user-images.githubusercontent.com/40337213/116117875-0520d680-a6bd-11eb-9085-acce6b56b395.png" width="600" height="100">   
  
       export MyTenant="1234.live.dynatrace.com"
       export MyToken=<your token> 

   **dynatrace saas tenant** (and free trial) : "1234.live.dynatrace.com" (without **https://** and **/** at the end of the line)   
   **dynatrace managed tenant** : "1234.dynatrace-managed.com/e/abc123etc" (without **https://** and **/** at the end of the line)   
    
    
6) validate the main variables for monaco   

       echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken

7) start with a backup of the configuration    
 monaco will backups your main Dynatrace configuration  
 the directory **free_trial** is created localy (lab_monaco/free_trial) with all you json configuration files exported.  
 
       cd;cd easy-dynatrace-with-monaco;
       ./monaco download -e=environments.yaml mydownload
 
 - look at the configuration types backuped by monaco   

       cd;cd easy-dynatrace-with-monaco;
       ls -lrt mydownload/free_trial
       
       
8) troubleshoot

| Step  | test |Status |
| --------------- | --------------- | --------------- | 
| export NEW_CLI=1 | echo "NEW_CLI="$NEW_CLI  | ✔️ |
| export MyTenant=1234.live.dynatrace.com | echo "MyTenant=https://"$MyTenant  | ✔️ |
| export MyToken=abcd1234xyz| echo "MyToken="$MyToken | ✔️ |
| OneAgent installed with host-group=appname | service oneagent status | ✔️ |
| easytravel installed and started (accessible from your browser) | docker ps --format "{{.ID}}\t{{.Status}}\t{{.Names}}" | ✔️ |
| cd;git clone https://github.com/dynatrace-ace-services/easy-dynatrace-with-monaco (this lab) | cd;ls -lrt easy-dynatrace-with-monaco | ✔️ |
| monaco installed with NEW_CLI=1 (new monaco cli version) | cd;cd easy-dynatrace-with-monaco;./monaco --version  | ✔️ |
| monaco download -e=environments.yaml mydownload (for backup) | cd;ls -lrt easy-dynatrace-with-monaco/mydownload/free_trial | ✔️ |

# Next Step

- [01-deploy-Config](https://github.com/dynatrace-ace-services/easy-dynatrace-with-monaco/tree/main/01-deploy-Config) => to deploy all the configuration for easytravel on your tenant  

