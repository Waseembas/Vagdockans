Steps

clone the repo 

get the full path where is code clone


config.vm.synced_folder "paste the your system repo complete path here", "/home/ubuntu"

vagrant up

vagrant ssh




these following lines are automated with vagrant

"
install the ansible on your system first by this link https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-ansible-on-ubuntu-16-04
now check the connectivity using this command ansible -m ping localhost
install the docker and dockercompose using these links

https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-16-04
https://www.digitalocean.com/community/tutorials/how-to-install-docker-compose-on-ubuntu-16-04

after the installation

clone this repo

go inside Assinment/docker_project folder and build the golang api and wordpress server on the localhost its mean it will build api and wordpress locally in dockers.
for wordpress we are using dockercompose because we are using db service on seperate docker.

run this command

sudo ansible-playbook  main.yml -vvv

this will your you both servers in dockers.

after deployment

get your host ip as ifconfig or ipconfig

for golang api use http://172.17.0.2:8080/todos
then you will reponce some thing like that
[{"id":1,"name":"Write presentation","completed":false,"due":"0001-01-01T00:00:00Z"},{"id":2,"name":"Host meetup","completed":false,"due":"0001-01-01T00:00:00Z"}]

for wordpress  

Go to http://172.17.0.2/wp-admin/

Admin user credentials:

login: admin
password: admin

"







REmaining will move in jenkin vagrant automation repo

For ASSIGMENT part


mkdir /var/jenkins_home
sudo  docker pull jenkins
sudo docker run -itd --name myjenkn -p 8080:8080 -p 50000:50000 -v /var/jenkins_home jenkins
now jenkins up and running

The second step is to make certificates
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/nginx/ssl/server.key -out /etc/nginx/ssl/server.crt

Then install nginx

for ubuntu

sudo apt-get install nginx

go the this location and flush the default file and copy the nginx.conf file conf in to the default. nginx.conf present in repo please check
/etc/nginx/sites-enabled/default

change this line to localip as 
server your_system_ip:8080 fail_timeout=0

after close and save restart the nginx server

service nginx restart


in my case url is https://192.168.10.5/login?from=%2F

go to this location of your system cat /var/jenkins_home/secrets/initialAdminPassword
copy the password and past on the https://192.168.10.5/login?from=%2F login page.Pleae also see the picture 1.

For User Tracking we will use Martrix bases auth plugins


