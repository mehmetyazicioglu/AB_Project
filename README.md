# AB_Project
AB Project
first of all, we need to build our on Jenkins docker image in order to skip initial setup manually and enabled user login in order to access jenkins. 


cd jenkins

docker build -T {{ any name you want to use }}


In order to run jenkins server as docker container, we need to install neccassary packages, for this using ansible in order to automate everything in order to run jenkins-server as a container in Virtual Host. You can pass jenkins username and password as extra vars or you can use ansilbe vault to crypt user name and password. sample command is:

ansible-playbook  ab_project.yml  --ask-become-pass --extra-vars "admin_id={{ user_name }}  password= {{ password }}"


![alt text](https://github.com/mehmetyazicioglu/AB_Project/blob/main/ab_project.png)

