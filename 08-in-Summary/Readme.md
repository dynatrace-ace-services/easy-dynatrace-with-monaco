# 08-in-Summary 
it's what you can import in your Jenkins to automate your monitoring :  

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
- [09-next-Step](https://github.com/ace-dynatrace-lab/ace-monitoring-as-code/tree/main/09-next-Step) => now you are ready to integrate Dynatrace configuration to your CICD pipeline.
