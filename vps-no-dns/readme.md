# RUN THIS ON VPS

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


## Edit `nginx.conf` file 

and add place Husarnet IPv6 address of a Husarnet Client running on Raspberry Pi in this field:

```
server {  
    listen 8089;
    listen [::]:8089;

    location / {
        set $myupstream http://[fc94:f4b2:9ffc:c3a5:93b4:b873:9ae1:67da]:8080;
        proxy_pass $myupstream;
    }
}
```

## run the container

```bash
cd vps-no-dns
docker-compose-up
```

Right now you should be able to access the sample webserver app, by using this URL from a level of any devices from the same Husarnet network the sample web server was joined to:

```
http://my-website:8080/
```
