## Obtaining an image from docker and building it:

1. Oopen Gitbash and run the following command:

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

