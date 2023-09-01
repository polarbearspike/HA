# HA
Home Assistant Docker compose file


Installation:
ssh into the rpi 
enter the following commands

sudo apt update && sudo apt-full upgrade -y
mkdir homeassistant && cd homeassistant
wget https://raw.githubusercontent.com/polarbearspike/HA/main/docker-compose.yml
docker compose up -d

if docker compose up -d throws an error, it will either be because your user isn't in the docker group OR because you're running the deprecated version of docker compose.  

if the username isn't working, you can either run it as superuser:
sudo docker compose up -d

or add your user to the docker group and then run it:

sudo usermod -aG docker $USER
docker compose up -d

if you're running the deprecated version of docker compose, instead use:
docker-compose up -d



