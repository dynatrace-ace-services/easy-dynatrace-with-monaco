# 07-delete-Config

1) validate your env variables  

       echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "Appname="$Appname;
  
2) delete your configiration  
 Don't worry, it will delete only the configuration from monaco_lab and not your others Dynatrace configurations ;)   

       cd;cd ace-monitoring-as-code;
       sed -i 's/Appname/'$Appname'/g' 07-delete-Config/delete.yaml;./monaco deploy -e=environments.yaml -s=free_trial 07-delete-Config;sed -i 's/'$Appname'/Appname/g' 07-delete-Config/delete.yaml
       
3) if you need to re-deploy it very quicly use these commands  

- export the variables

      export MyTenant=https://abcd.live.dynatrace.com
      export MyToken=ABCD123456XYZ
      export Appname=<Host_Group>
      export Hostname=<myhostname.domaine.com>
      export Email=myemail@email.com
      export EnableSynthetic=true
      export Owner=$Email

- env variables  

      echo "MyTenant="$MyTenant;echo "MyToken="$MyToken;echo "Appname="$Appname;echo "Hostname="$Hostname;echo "EnableSynthetic="$EnableSynthetic;echo "Owner="$Owner

- deploy with monaco  

      cd;git clone https://github.com/ace-dynatrace-lab/ace-monitoring-as-code.git;cd ace-monitoring-as-code;chmod +x monaco;export NEW_CLI=1;
      ./monaco deploy -e=environments.yaml -s=free_trial 01-deploy-Config;
      ./monaco deploy -e=environments.yaml -s=free_trial 03-enable-Synthetic;
      ./monaco deploy -e=environments.yaml -s=free_trial 04-import-Dashboards;
      ./monaco deploy -e=environments.yaml -s=free_trial 05-calculate-Slo/Metric;
      ./monaco deploy -e=environments.yaml -s=free_trial 05-calculate-Slo/Slo;
      ./monaco deploy -e=environments.yaml -s=free_trial 06-define-Requestattribute
 
# Next Step
- [08-next-Step](https://github.com/ace-dynatrace-lab/ace-monitoring-as-code/tree/main/08-next-Step) => now you are ready to integrate Dynatrace configuration to your CICD pipeline.
