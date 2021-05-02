# 07-delete-Config

1) validate your env variables  

       echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "Appname="$Appname;
  
2) delete your configiration  
 Don't worry, it will delete only the configuration from monaco_lab and not your others Dynatrace configurations ;)   

       cd;cd ace-monitoring-as-code;
       sed -i 's/Appname/'$Appname'/g' 07-delete-Config/delete.yaml;./monaco deploy -e=environments.yaml -s=free_trial 07-delete-Config;sed -i 's/'$Appname'/Appname/g' 07-delete-Config/delete.yaml
       

# Automate these steps 
now you can import these steps in your Jenkins :  

      
- export the variables

      export NEW_CLI=1;
      export MyTenant=https://abcd.live.dynatrace.com
      export MyToken=ABCD123456XYZ
      export Appname=<Host_Group>
      export Hostname=<myhostname.domaine.com>
      export Email=myemail@email.com
      export EnableSynthetic=true
      export Owner=$Email

- update the config

       cd;
       cd ace-monitoring-as-code;
       git pull

- deploy the config

      ./monaco deploy -e=environments.yaml -s=free_trial 01-deploy-Config;
      ./monaco deploy -e=environments.yaml -s=free_trial 03-enable-Synthetic;
      ./monaco deploy -e=environments.yaml -s=free_trial 04-import-Dashboards;
      ./monaco deploy -e=environments.yaml -s=free_trial 05-calculate-Slo/Metric;
      ./monaco deploy -e=environments.yaml -s=free_trial 05-calculate-Slo/Slo;
      ./monaco deploy -e=environments.yaml -s=free_trial 06-define-Requestattribute
 
# Next Step
- [08-next-Step](https://github.com/ace-dynatrace-lab/ace-monitoring-as-code/tree/main/08-next-Step) => now you are ready to integrate Dynatrace configuration to your CICD pipeline.
