# HA
Home Assistant Docker compose file


Installation:
ssh into the rpi 
enter the following commands:


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


if the command works, you should see a progress bar downloading, unpacking, and spinning up the docker container, and it should return you to the CLI when container is started.  

then run:
ifconfig

it should give you a wall of text, look for the entry by either eth0 (if you are using wired ethernet) or wlan0 (if you are using wifi) (it will probably be something like 192.168.1.x  This is your server IP.  

at this point, type "exit" to end the ssh session

return to regular computer, and open a web browser and navigate to (replace the [SERVER IP HERE] below with the IP address you just found above):  
http://[SERVER IP HERE]:8123

should open a setup page for home assistant.  

for best results, at this point you should hop into your router and make the IP address static for your server, so that you always know what address to navigate to.  

once you set up username/password, you can also install the ios app and point it at your server (won't work while you are off your local wifi/network, unless you poke holes in your firewall, which is slightly more complicated and dangerous).  






