# AB_Project
AB Project
first of all, we need to build our on Jenkins docker image in order to skip initial setup manually and enable secure jenkins to user login to Jenkins. it also setup initial configuration and neccassary plugins for our project.

we need to checkout our proect to our localhost and go to repository.

cd jenkins

docker build -t {{ any name you want to use }}

docker tag {{ image id }} 

docker push {{ image name }} 

custom AB project jenkins docker hub url --> 

https://hub.docker.com/repository/docker/mehmetyazicioglu/jenkins_ab_project

In order to run jenkins server as a docker container, we need to install neccassary packages, for this using ansible in order to automate everything in order to run jenkins-server as a container in Virtual Host. You can pass jenkins username and password as extra vars or you can use ansilbe vault to crypt user name and password. sample command is:

ansible-playbook  ab_project.yml  --ask-become-pass --extra-vars "admin_id={{ user_name }}  password= {{ password }}"

After setting up jenkins as a container in local environment. it is time to build metricbeat, elasticsearch, kibana and logstash custom docker images.

1- Elasticsearch repo --> https://github.com/mehmetyazicioglu/elasticsearch

2- Kibana repo --> https://github.com/mehmetyazicioglu/kibana

3- Logstash repo --> https://github.com/mehmetyazicioglu/logstash

4- Metric repo --> https://github.com/mehmetyazicioglu/metricbeat

Images are pushed to docker hub:

https://hub.docker.com/r/mehmetyazicioglu/kibana
https://hub.docker.com/repository/docker/mehmetyazicioglu/logstash
https://hub.docker.com/repository/docker/mehmetyazicioglu/elasticsearch
https://hub.docker.com/repository/docker/mehmetyazicioglu/metricbeat

after images successfully built by jenkins job, all subjected jobs are automatically triggers to ELK_STACK job to run ELK components in together. 
ELK stack repo --> https://github.com/mehmetyazicioglu/ELK_stack



![alt text](https://github.com/mehmetyazicioglu/AB_Project/blob/main/ab_project.png)

