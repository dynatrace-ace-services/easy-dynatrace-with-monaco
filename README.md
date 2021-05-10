#  Automate Cloud for all : How to configure dynatrace with Monaco

In this lab, you will automatically deploy the smart configuration for easytravel.  
You just need a linux with docker and a Dynatrace free trial environment.  
This lab has been tested with linux Ubuntu 16.04 on Azure.  

# Prerequisite : OneAgent and easytravel

1) get your Dynatrace free trial  

      https://www.dynatrace.com/trial/    

2) install dynatrace OneAgent on your host 
([oneagent installation documentation](https://github.com/ace-dynatrace-lab/loadtesting-lab/blob/main/InstallEasytravel.md))    

       Go to your Dynatrace free trial > Dynatrace Hub > OneAgent Linux (https://abcd.live.dynatrace.com/#install;gf=all),
       and follow the workflow :
       1)  Download the installer using this command on the target host: 
             wget  -O Dynatrace-OneAgent-Linux-1.xxx.sh ...
       2)  Verify signature (optional)
       3)  Set customized options:
           - host-group => easytravel00 
           - properties => env=sandbox
       4) Run the installer with root rights : 
            sudo /bin/sh Dynatrace-OneAgent-Linux-1.213.155.sh --set-host-group=easytravel00 --set-host-property=env=sandbox

- be sure to configure a host-group during this installation. In this example **host-group=easytravel00**

3) install easytravel docker   
- test if easytravel is already installed (it could be the case for the training and quickstart environment)   

      docker ps --format "{{.ID}}\t{{.Status}}\t{{.Names}}"

- if you have this result, you don't need to install easytravel  
  ![image](https://user-images.githubusercontent.com/40337213/116451621-02f57e00-a85d-11eb-96a0-c1d0613185c7.png)
   
      skip this step
            
- if not, install easytravel 

      cd;git clone https://github.com/Dynatrace/easyTravel-Docker;
      cd easyTravel-Docker;
      export ET_APM_SERVER_DEFAULT=APM;
      docker-compose up -d

more info here : https://github.com/Dynatrace/easyTravel-Docker  
  
4) from your browser you can access to easytravel  

       http://<myhostname.domain.com>

5) restart easytravel ?  
Go to your dynatrace environment : *Deployment status > OneAgents*, if there is a warning wih the message process **isn't monitored**, you have to restart easytravel. It's the case when the oneagent is installed after the application :  
    <img src="https://user-images.githubusercontent.com/40337213/116455523-713c3f80-a861-11eb-8786-0858aa10512c.png" width="600" height="200">

- restart easytravel docker

      export ET_APM_SERVER_DEFAULT=APM;
      docker-compose down;
      docker-compose up -d
       
  ![image](https://user-images.githubusercontent.com/40337213/116609980-4c190100-a935-11eb-9fd0-d0739d13cb03.png)


# Labs 

- [00-install-Monaco ](https://github.com/dynatrace-ace-services/easy-dynatrace-with-monaco/tree/main/00-install-Monaco) => to install monaco and connect it to your dynatrace free trial environment   
- [01-deploy-Config](https://github.com/dynatrace-ace-services/easy-dynatrace-with-monaco/tree/main/01-deploy-Config) => to deploy all the configuration for easytravel on your tenant  
- [02-add-Javascriptframeworks](https://github.com/dynatrace-ace-services/easy-dynatrace-with-monaco/tree/main/02-add-Javascriptframeworks) => to enable "jQueries", "ICEfaces" and "Prototype" javascript framework  
- [03-enable-Synthetic](https://github.com/dynatrace-ace-services/easy-dynatrace-with-monaco/tree/main/03-enable-Synthetic) => to enable both synthetic monitor and synthetic browser  
- [04-deploy-Dashboards](https://github.com/dynatrace-ace-services/easy-dynatrace-with-monaco/tree/main/04-import-Dashboards) => to deploy "Dynatrace: Smarter Simple" dashboard  
- [05-calculate-Slo](https://github.com/dynatrace-ace-services/easy-dynatrace-with-monaco/tree/main/05-calculate-Slo) => to generate and calculate Slo  
- [06-define-Requestattribute](https://github.com/dynatrace-ace-services/easy-dynatrace-with-monaco/tree/main/06-define-Requestattribute) => to create a business entity inside the service views
- [07-delete-Config](https://github.com/dynatrace-ace-services/easy-dynatrace-with-monaco/tree/main/07-delete-Config) => to delete the configuration deployed in the previous lab    
- [08-in-Summary](https://github.com/dynatrace-ace-services/easy-dynatrace-with-monaco/tree/main/08-in-Summary) => it's an overview of the task you can easily automate.
- [09-next-Step](https://github.com/dynatrace-ace-services/easy-dynatrace-with-monaco/tree/main/09-next-Step) => now you are ready to integrate Dynatrace configuration to your CICD pipeline.
