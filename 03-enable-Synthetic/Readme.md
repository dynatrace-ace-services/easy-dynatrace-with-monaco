# 03-enable-Synthetic
In this lab we will deploy a synthetic http monitor and a synthetic browser monitor. In a first step both synthetic monitors will be disabled, we will enable them in a second step.

1) export the variable 

       export EnableSynthetic=false

2) verify your env  

       echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "Appname="$Appname;echo "Hostname="$Hostname;echo "EnableSynthetic="$EnableSynthetic
       
3) deploy the config  

       cd;cd monitoring-as-code;
       ./monaco deploy -e=environments.yaml -s=free_trial 03-enable-Synthetic
       
4) verify the result on your dynatrace environment : _Synthetic_  

![image](https://user-images.githubusercontent.com/40337213/116456772-e9efcb80-a862-11eb-8157-e99dadc32ba7.png)


5) enable the config 

       export EnableSynthetic=true;
       cd;cd monitoring-as-code;
       ./monaco deploy -e=environments.yaml -s=free_trial 03-enable-Synthetic
       
5) verify the config is enable     
![image](https://user-images.githubusercontent.com/40337213/115127877-425cd880-9fda-11eb-905e-6ebe6d01ef93.png)

* the synthetic result is mapped with your application. Synthetic is the way to monitor the application availability.   
![image](https://user-images.githubusercontent.com/40337213/115962170-62c8ed80-a51a-11eb-9f81-ae05684e7c5d.png)

# Next Step
- [04-deploy-Dashboards](https://github.com/dynatracelab/monitoring-as-code/tree/main/04-import-Dashboards) => to deploy "Dynatrace: Smarter Simple" dashboard  
