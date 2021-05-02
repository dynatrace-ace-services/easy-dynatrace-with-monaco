- if you already have an esytravel on your host, skip this step.
- easytravel docker : installataion
more info here : https://github.com/Dynatrace/easyTravel-Docker  

      cd;git clone https://github.com/Dynatrace/easyTravel-Docker
      cd easyTravel-Docker
      export ET_APM_SERVER_DEFAULT=APM
      docker-compose up -d
  
- if you install the oneagent after starting  easytravel, you have to restart easytravel: 

      export ET_APM_SERVER_DEFAULT=APM
      docker-compose down
      docker-compose up -d
