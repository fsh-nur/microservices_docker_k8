## Obtaining an image from docker and building it:

1. Open Gitbash and run the following command:

```
$ docker run -d  -p 80:80 nginx

```
- In this command:
  - `-p` = in port:
  - `-d` = detached

- This runs nginx web server in your local host able to acces it through this: `http://localhost`


## You can open a shell within the web server:

1. Enter the following command to open a shell:
- Where `winpty` enables windows users to open the shell
- ` a87fa8258260` is the ID of the container which can be obtained using `docker ps`
```
$ winpty docker exec -it a87fa8258260 sh

```
2. Navigate to the following directories:

```
cd /usr
cd share
cd nginx
cd html
```

3. To enable `sudo` in your system:

```
apt-get install sudo
apt update
sudo apt-get install nano
sudo apt update
```

4. To enter the `index.html` file:

```
sudo nano index.html
```

Now we can make changes on the website such as this:


![Screenshot_1](https://github.com/fsh-nur/microservices_docker_k8/assets/129324316/ecabb353-80a2-48ff-af9d-d46689afd838)


## Automating the creation of a docker image using a `DockerFile`

1. Create a `Dockerfile` in your local directory

```
nano dockerfile
```

2. Input the following code withing your `dockerfile`

```
FROM nginx
LABEL MAINTAINER=FATIMA@SPARTA
COPY index.html /usr/share/nginx/html/
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
# docker build
#docker images to confirm the name
#docker run image name
#docker ps as well as localhost

```

3. Now we build our image 

```
docker build -t fshei/fatima_profile .
```
`fshei` - my repository on dockerhub
`fatima_profile` - the name of my image
`.` - don't forget the `.` at the end letting it know to build from your local host

4. Now we check if our image has built

```
docker images
```
5. Check the container

```
docker ps
```

6. Run the container on `port:80`

```
 docker run -d -p 80:80 fshei/fatima_profile

```
7. Now we push to dockerhub

```
 docker push fshei/fatima_profile

```

## Creating in image for our app:

1. Make sure that there is nothing running on `port:80` as we will be using this
2. Create a directory and move your `app` and `environment` folder there
3. Create a `Dockerfile` and input the following code:

```
nano Dockerfile
```
```
FROM node:16
LABEL MAINTAINER=fatima@sparta
COPY app/ .
Expose 3000
RUN npm install
CMD ["node", "app.js"]

```

4. Now run a `build` 

```
docker build -t fshei/node-app
```

5. Run the app

```
docker run -d -p 80:3000 fshei/node-app
```

6. Push to DockerHub

```
docker push fshei/node-app
```

7. You should see the page when naviagting to your local host


![reversre](https://github.com/fsh-nur/microservices_docker_k8/assets/129324316/b8d184ce-c4cc-4aa7-9ffe-f963d048a38f)


