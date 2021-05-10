# 05-calculate-Slo  

In this lab we will generate and calculate SLO for :  
- Application = (ApdexCategory=Success / All User action) % filtered on  the application easytravel  
- Service Performance = (request count < 100 ms  / All request count) % filtered on JourneyService  
	*for this SLO we will create a calculated service metric = request count < 100 ms for JourneyService*
	
- Service Availability = (request not in error  / All request count) % filtered on JourneyService  
- Synthetic = (availability) % - filtered on Clickpath

       
1) verify your env variables 

       echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "Appname="$Appname

2) load the calculated service metric first   

       cd;cd easy-dynatrace-with-monaco;
       ./monaco deploy -e=environments.yaml -s=free_trial 05-calculate-Slo/Metric
 
3) load the slo rules   

       cd;cd easy-dynatrace-with-monaco;
       ./monaco deploy -e=environments.yaml -s=free_trial 05-calculate-Slo/Slo
 
 4) verify on the result on your Dynatrace environment : _SLOs_

![image](https://user-images.githubusercontent.com/40337213/115956048-f4c0fe00-a4fa-11eb-97c1-95e1e2aed067.png)  
Add these SLO in your dashboard  

# Next Step
- [06-define-Requestattribute](https://github.com/dynatrace-ace-services/easy-dynatrace-with-monaco/tree/main/06-define-Requestattribute) => to create a business entity inside the service views
