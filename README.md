# Task
Containerise the react app using docker and docker image  

FINAL OUTPUT 
```bash
18.223.30.11
```

# Let's Start
### I'm using AWS Instance ubuntu 22.04
## Follow These steps
Make sure u have port 3000 aceesible on your instance or local machine 
```bash
sudo apt update -y && sudo apt upgrade -y
```
![update & upgrade ](https://github.com/offender6969/aesthiesia-demo/blob/main/images/1%20update%20the%20server.png)  

### Install Docker

```bash
sudo snap install docker.io -y
```
![dockerinstall](https://github.com/offender6969/aesthiesia-demo/blob/main/images/2installing%20docker.png)  
### Clone React App Source Code
follow this link for react app ** [Source Code](https://github.com/Aesthisia/Assignment-L1-DO)  
```bash
git clone https://github.com/Aesthisia/Assignment-L1-DO
```  
![gitcloneimg](https://github.com/offender6969/aesthiesia-demo/blob/main/images/3%20clone%20the%20repo%20and%20move%20the%20dir%20to%20home%20dir.png)  

```bash
ls
```
```bash
cd Assignment-L1-DO-Aesthisia
```
### its Optional (i just did this to take source code speratly   )
```bash
mv aesthisia-demo ../
```
```bash
cd ..
```
### Go to inside aesthisia-demo directory

```bash
cd aesthisia-demo
```
### make Docker file inside 
```bash
nano  Dockerfile
```
Write Docker File & You Can also paste these code  

```bash
FROM node:16
WORKDIR /aesthisia-demo
COPY package.json .
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm","start"]

```  
![dockerfile](https://github.com/offender6969/aesthiesia-demo/blob/main/images/5%20building%20the%20docker%20image.png)  

### build Docker File 
```bash
docker build -t react-img .
```  
![dockerbuild](https://github.com/offender6969/aesthiesia-demo/blob/main/images/6%20building%20the%20container%20from%20image.png)  

```bash
docker run -d -p 3000:3000 (your image name) 
```
![app](https://github.com/offender6969/aesthiesia-demo/blob/main/images/7%20WELCOME%20TO%20AESTHISIA.png)  

### enjoy 
yourIP:3000
