# 06-define-Requestattribute  

In this lab we will generate a request attribute to extract NewDestinationName parameter from the method  FindJourneysByLocation.  
With this request attribute, you will be abble to display a chart with the favorite destination "Paris, New-York etc" 
and you will filter the service flow view on a specific destination. 
       
1) verify your env variables

       echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "Appname="$Appname

2) enable the **Real Time Update for Java** : _Settings > Server-side service monitoring > Deep monitoring  > Real-time updates to Java services_   
 <img src="https://user-images.githubusercontent.com/40337213/116608882-fdb73280-a933-11eb-8c36-e2415ff6293d.png" width="700" height="150">

2) generate the request attribue **easytravel-findJourneyByLoaction**  

       cd;cd ace-monitoring-as-code
       ./monaco deploy -e=environments.yaml -s=free_trial 06-define-Requestattribute
 
3) verify on your dynatrace environment : _Transactions and services + filter on Request Attribute:easytravel00-findJourneyByLoaction_    
![image](https://user-images.githubusercontent.com/40337213/115960474-f1853c80-a511-11eb-8f17-9fd7a03f4712.png)

4) create your chart :
- Open _Diagnostic tools > Top Web requests_ and split by your request attribute   
![image](https://user-images.githubusercontent.com/40337213/115960286-cb12d180-a510-11eb-9c8c-fedc059dc8e9.png)

- Create a metric, (delete the filter webservice, add your management zone and create your new metric) 
![image](https://user-images.githubusercontent.com/40337213/115960254-9d2d8d00-a510-11eb-9eb0-0730c493f500.png)

- Wait 5 minutes after creating your metric to have your fisrt data collected. (it's a new metric, there is no historical data here).  
- Go to metric menu and filter on the request attribute **easytravel-findJourneyByLoaction**: 
![image](https://user-images.githubusercontent.com/40337213/115960736-6016ca00-a513-11eb-80e3-89c52282a245.png)

- Create chart : split by dimension and display on a table view
![image](https://user-images.githubusercontent.com/40337213/115960767-89375a80-a513-11eb-94ab-aad1748df587.png)

5) you can find this method here in the method hotspot, the parameter1 *String NewDestinationName* is the one which is collected :
![image](https://user-images.githubusercontent.com/40337213/115960649-f4346180-a512-11eb-9929-e19a84242b1f.png)

6) download the classe and open the source code  :
![image](https://user-images.githubusercontent.com/40337213/115960550-5d67a500-a512-11eb-90fc-940e200c5107.png)
Use your favorire decompilator tool to openthe source code (or for demo only use a online decompilator: http://www.javadecompilers.com)

# Next Step 
- [07-delete-Config](https://github.com/ace-dynatrace-lab/ace-monitoring-as-code/tree/main/07-delete-Config) => to delete the configuration deployed in the lab_monaco   
