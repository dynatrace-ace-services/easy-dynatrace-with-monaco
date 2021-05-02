# 02-add-Javascriptframeworks


In this lab we will enable javascript frameworks **jqueries**, **icefaces** and **prototype** on our application easytravel.

1) edit the json file configuration : lab-app-web.json
- with nano

      cd;cd monitoring-as-code;
      nano 02-add-Javascriptframeworks/application-web/lab-app-web.json
 
 - or with vi
 
       cd;cd monitoring-as-code; 
       vi 02-add-Javascriptframeworks/application-web/lab-app-web.json
      
 - turn to true the configuration like this  
  ![image](https://user-images.githubusercontent.com/40337213/115123400-2991fa00-9fbd-11eb-912c-1f251726cbbd.png)  
  

2) validate your env variables 

       echo "NEW_CLI="$NEW_CLI;echo "MyTenant=https://"$MyTenant;echo "MyToken="$MyToken;echo "Appname="$Appname
       

3) deploy the config 

       cd;cd monitoring-as-code;
       ./monaco deploy -e=environments.yaml -s=free_trial 02-add-Javascriptframeworks
       
4) expected result

  ![image](https://user-images.githubusercontent.com/40337213/116594390-71e8da80-a922-11eb-8322-dd58e900c018.png)
  

5) verify the configuration on the Dynatrace environment : _Application > Setting / Async web requests and SPAs_  

 ![image](https://user-images.githubusercontent.com/40337213/115123441-5d6d1f80-9fbd-11eb-81ee-86f0dbba78a6.png)


# Next Step
- [03-enable-Synthetic](https://github.com/dynatracelab/monitoring-as-code/tree/main/03-enable-Synthetic) => to enable both synthetic monitor and synthetic browser
