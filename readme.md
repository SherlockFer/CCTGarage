## HOW TO DEPLOY
1. Install Docker. In terminal execute code: 
```
brew cask install docker
```
2. Create data folder for MariaDB
```
sudo mkdir -p /var/docker
sudo chmod 777 /var/docker
```    
3. Start Docker from Finder->Applications and wait until Docker is initialized (Whale icon on top bar)
4. Add data folder to Docker's FileSharing
```
Click Docker-Icon->Preferences->FileSharing. Add: /var/docker
```
5. Deploy Docker admin tool: Portainer. Go to http://localhost:9000 and set user/pass to admin/superadmin 
```
docker run -d -p 9000:9000 --name portainer --restart always -v /var/run/docker.sock:/var/run/docker.sock portainer/portainer  
```
6. Install Docker Compose. In terminal execute
```
brew install docker-compose
```
7. Clone the application from Github 
```
git clone https://github.com/SherlockFer/garage.git
cd garage
```    
8. Start-up the application. If some db error messages appears at `rake db:reset`, try again `make up` 
```
make up
```
9. Enjoy:
```
Web: http://localhost
Api: http://localhost:3000/swagger
```
