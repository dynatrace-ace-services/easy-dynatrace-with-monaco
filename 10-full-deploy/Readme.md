# 10-full-deploy

You will import :  
- application-web 
- app-detection-rule 
- management-zone
- autotag
- alerting-profile 
- notification
- maintenance-window
- host-naming
- processgroup-naming
- sevice-naming
- dashboard
- synthetic
- calculated service metric
- slo

1) your variables  
	   
	   export NEW_CLI=1
	   export MyTenant=<YYYY>.live.dynatrace.com
	   export MyToken=<dt.1234567890>
	   export Appname=easytravel<XX>
	   export Hostname=dynatracelab<XX>.<AzureRegion>.cloudapp.azure.com
	   export Email=<your email of Dynatrace saas tenant connection>

  
2) validate the env variables 

       echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "Appname="$Appname;echo "Hostname="$Hostname;echo "Email="$Email 

3) deploy the configuration 

       cd;cd easy-dynatrace-with-monaco/
       ./monaco deploy -e=environments.yaml 10-full-deplo/Deploy
	   ./monaco deploy -e=environments.yaml 10-full-deplo/Slo
