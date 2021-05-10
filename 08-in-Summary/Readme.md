# 08-in-Summary 
it's what you can define in your Jenkins Pipeline to automate your monitoring :  

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
      cd easy-dynatrace-with-monaco;
      git pull

- deploy the config

      ./monaco deploy -e=environments.yaml -s=free_trial 01-deploy-Config;
      ./monaco deploy -e=environments.yaml -s=free_trial 03-enable-Synthetic;
      ./monaco deploy -e=environments.yaml -s=free_trial 04-import-Dashboards;
      ./monaco deploy -e=environments.yaml -s=free_trial 05-calculate-Slo/Metric;
      ./monaco deploy -e=environments.yaml -s=free_trial 05-calculate-Slo/Slo;
      ./monaco deploy -e=environments.yaml -s=free_trial 06-define-Requestattribute
 
# Next Step
- [09-next-Step](https://github.com/dynatrace-ace-services/easy-dynatrace-with-monaco/tree/main/09-next-Step) => now you are ready to integrate Dynatrace configuration to your CICD pipeline.
