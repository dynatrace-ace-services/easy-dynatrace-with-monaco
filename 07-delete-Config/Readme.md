# 07-delete-Config

1) validate your env variables  

       echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "Appname="$Appname;
  
2) delete your configiration  
 Don't worry, it will delete only the configuration from monaco_lab and not your others Dynatrace configurations ;)   

       cd;cd ace-monitoring-as-code;
       sed -i 's/Appname/'$Appname'/g' 07-delete-Config/delete.yaml;./monaco deploy -e=environments.yaml -s=free_trial 07-delete-Config;sed -i 's/'$Appname'/Appname/g' 07-delete-Config/delete.yaml
       
# Next Step
- [08-in-Summary](https://github.com/ace-dynatrace-lab/ace-monitoring-as-code/tree/main/08-in-Summary) => it's an overview of the task you can easily automate.
