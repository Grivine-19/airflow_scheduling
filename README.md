# Creating DAGs With Airflow - Docker Installation

## Install steps
### NB: *Assumes that you have the latest version of Docker and Docker compose installed in your system.*
a.  *Create a folder trough the terminal and run the following command to download
the official docker compose file created by Airflow on their official site: curl -LfO 'https://airflow.apache.org/docs/apache-airflow/2.1.0/docker-compose.yaml'*

b.  *Create three folders in the same folder where the compose file is downloaded: mkdir ./dags ./logs ./plugins*

c.  *Grant access to the logs folder: chmod -R 777 /logs*

d.  *create a .env file that is going to contain the environment variable: echo -e “AIRFLOW_UID=$(id -u)\nAIRFLOW_GID=0” > .env*

e.  *Execcute the command: docker-compose up airflow-init and wait for magic to happen*

f.  * To remove example DAGs from the webserver, edit the compose file using: nano docker-compose.yaml then set AIRFLOW__CORE__LOAD_EXAMPLES: 'false'  

g.  *Run the command: docker-compose up to see that airflow is up and running*

h.  *If you want to stop airflow in a terminal execute the command: docker-compose down*

i.  *To test  your DAG tasks run: docker-compose run airflow-worker airflow tasks test <DAG_Name> <Task_Id>*
