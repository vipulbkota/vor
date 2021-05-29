
![](https://pbs.twimg.com/profile_images/1273307847103635465/lfVWBmiW_400x400.png)


Project dependencies:

* [flask](http://flask.pocoo.org)
* [peewee](http://docs.peewee-orm.com)
* [pygments](http://pygments.org)


### Screenshots

The first step is to clone the application into our repsitory

All dependencies and required files are present in repository our job is to just build the image and deploy the docker.

Build image:

`docker build -t coleifer/sqlite-web.`

![](https://raw.githubusercontent.com/vipulbkota/vor/main/build.PNG)

Then finally deploy it using docker run:

`docker run -it --rm -p 8080:8080  -e SQLITE_DATABASE=vorbio.db coleifer/sqlite-web`



Finally application deployed on local host:


![](https://raw.githubusercontent.com/vipulbkota/vor/main/final.PNG)
