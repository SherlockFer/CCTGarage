## Technology Project

URL Login: http://www.moshimoshiaqp.com/

Swagger API Spec: http://www.moshimoshiaqp.com:3000/swagger 
Token(email: admin@garage.com / password: 123456)

1. Final Project Overview
2. How to Deploy


## 1. Final Project Overview

1. Project's Name
```
Ger's Garage
```
2. Business description
```
Ger's Garage is a small garage where carries out maintenance checks for all kinds of small to medium vehicles.
```

3. Project's requirement desciption
```
Customers can register on the website and book their vehicle in for a service.
Admin can manage the bookings. (see details requirement: detailsRequirement file)
```
4. Ger's Garage Web Application Description:
```
Ger's Garage's web application is a client server application in which the client runs in a web browser and they can book their vehicles for a service. Users can access the application from any computer connected to the internet, instead of using an application that has been installed on the user’s computer. Ger's Garage's web application can interact with users, by responding to users using REST API response structure using a specific HTTP method on a specific type of call made to the server.
```
5. Technology Stack:

Frontend
```
Angular2, Bootstrap4.
```
Backend
```
Ruby GrapeAPI, Swagger, Nginx, MariaDB.
```
Tools
```
AWS-EC2, Git, Docker, Docker-Compose, Portainer.
```

## 2. HOW TO DEPLOY
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
git clone https://github.com/SherlockFer/CCTGarage.git
cd CCTGarage
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
