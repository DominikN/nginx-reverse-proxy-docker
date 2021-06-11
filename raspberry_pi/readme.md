# RUN THIS ON YOUR LAPTOP / RASPBERRY PI

## create `.env` file

with the following content:

```bash
HOSTNAME=my-website
JOINCODE=fc94:b01d:1803:8dd8:b293:5c7d:7639:932a/xxxxxxxxxxxxxxxxxxxxxx
```

where `fc94:b01d:1803:8dd8:b293:5c7d:7639:932a/xxxxxxxxxxxxxxxxxxxxxx` is your Husarnet network unique identifier allowing you to join it.


You will find your Join Code at **https://app.husarnet.com  
 -> Click on the desired network  
 -> `Add element` button  
 -> `Join Code` tab** 

## run the container

```bash
cd raspberry_pi
docker-compose-up
```

Right now you should be able to access the sample webserver app, by using this URL from a level of any devices from the same Husarnet network the sample web server was joined to:

```
http://my-website:8080/
```
