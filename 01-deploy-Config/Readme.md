# 01-deploy-Config

In this lab we will import these configurations in your Dynatrace environment.  

You will import :  
- application-web 
- app-detection-rule 
- management-zone
- autotag
- alerting-profile 
- notifiaction
- maintenance-window
- host-naming
- processgroup-naming
- sevice-naming

1) export the variables  

       export Appname=<Host_Group>
       export Hostname=<myhostnname.domain.com>
       export Email=monemail@email.com
  
2) validate the env variables 

       echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "Appname="$Appname;echo "Hostname="$Hostname;echo "Email="$Email 

- result  
![image](https://user-images.githubusercontent.com/40337213/116620595-542b6d80-a942-11eb-8c44-909b151c5500.png)
      
      
3) run monaco in drive mode (no action - just testing the command of monaco)  

       cd;cd ace-monitoring-as-code
       ./monaco deploy -d -e=environments.yaml -s=free_trial 01-deploy-Config

- result  
![image](https://user-images.githubusercontent.com/40337213/115118727-ef1c6300-9fa4-11eb-8ba4-55bee76a8c1d.png)

4) deploy the configuration (no drive mode)  

       cd;cd ace-monitoring-as-code
       ./monaco deploy -e=environments.yaml -s=free_trial 01-deploy-Config
       
5) verify on your Dynatrace environment the result of the imported configurations  
 
- **application-web and app-detection-rule** : _Settings > Web and mobile monitoring > Application detection_ 
![image](https://user-images.githubusercontent.com/40337213/116122980-b6763b00-a6c2-11eb-93f3-dde596728237.png)

- **management-zone** : _Settings > Preferences > Managelent Zones_ 
![image](https://user-images.githubusercontent.com/40337213/115960930-6c4f5700-a514-11eb-9b6d-952b86a17730.png)

- **autotag** : _Settings > Tags > Automatically applied tags_
![image](https://user-images.githubusercontent.com/40337213/115961025-e2ec5480-a514-11eb-9e7d-667f54ebf7a3.png)

- **alerting-profile** : _Settings > Alerting > Alerting profiles_
![image](https://user-images.githubusercontent.com/40337213/115961162-7c1b6b00-a515-11eb-9df8-69bec4a2c8ad.png)

- **notifiaction** : _Settings > Integration > Integrate Dynatrace with 3rd party systems_
![image](https://user-images.githubusercontent.com/40337213/115961294-1b406280-a516-11eb-83ec-689b7ccd90ee.png)

- **maintenance-window** : _Settings > Maintenance windows for monitoring, alerting and availability_
![image](https://user-images.githubusercontent.com/40337213/115961411-7a9e7280-a516-11eb-99eb-58d258e7a9f6.png)

- **host-naming** : _Settings > Monitoring > Host naming_  
 Click on Preview botton to display the result of this configuration 
![image](https://user-images.githubusercontent.com/40337213/116593772-c0e24000-a921-11eb-849b-849ee7050113.png)

- **processgroup-naming** : _Settings > Processes and containers > Process group naming_  
Click on Preview botton to display the result of this configuration 
![image](https://user-images.githubusercontent.com/40337213/116593829-d0618900-a921-11eb-951d-bbf3de4bcca1.png)

- **sevice-naming** : _Settings > Server-side service monitoring > Custom service detection_  
Click on Preview botton to display the result of this configuration 
![image](https://user-images.githubusercontent.com/40337213/116593961-fab34680-a921-11eb-896b-38852940446e.png)

       
# Next Step
- [02-add-Javascriptframeworks](https://github.com/ace-dynatrace-lab/ace-monitoring-as-code/tree/main/02-add-Javascriptframeworks) => "jQueries", "ICEfaces" and "Prototype" javascript framework
