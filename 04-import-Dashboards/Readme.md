# 04-import-Dashboards

In this lab we will import a dashboard.  

1) export the variable 

       export Owner=<your user account>
       
  - if Owner and Email are the same :  
   
        export Owner=$Email
       
2) verify your env variables 

       echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "Appname="$Appname;echo "Hostname"=$Hostname;echo "Owner="$Owner

3) deploy the dashboard   

       cd;cd ace-monitoring-as-code;
       ./monaco deploy -e=environments.yaml -s=free_trial 04-import-Dashboards
 
4) open your new dashboard : _Dashboard_

      **My awesome dasboard for easytravel !** 
 
 ![image](https://user-images.githubusercontent.com/40337213/116607293-19213e00-a932-11eb-9d12-a26173a4a7e7.png)

- Dynatrace dashboards : you can find more smart dashboards on bizopsconfigurator which is Open Source Software with a GitOps approach. 
And later you could share your own awesome dashboards on this plateform ==> [bizopsconfigurator](https://dynatrace.github.io/BizOpsConfigurator/index.html#miscTools)  

# Next Step
- [05-calculate-Slo](https://github.com/ace-dynatrace-lab/ace-monitoring-as-code/tree/main/05-calculate-Slo) => to generate and calculate SLO (Service level objectif)   
