
![](https://pbs.twimg.com/profile_images/1273307847103635465/lfVWBmiW_400x400.png)


Project dependencies:

* [flask](http://flask.pocoo.org)
* [peewee](http://docs.peewee-orm.com)
* [pygments](http://pygments.org)


### Screenshots

The first step is to clone the application into our repsitory

All dependencies and required files are present in repository our job is to just build the image and deploy the docker.

Build image:
![](https://ibb.co/9GZsfwj)

The `content` tab displays all the table data. Links in the table header can be used to sort the data:

![](http://media.charlesleifer.com/blog/photos/s1415479502.61.png)

The `query` tab allows you to execute arbitrary SQL queries on a table. The query results are displayed in a table and can be exported to either JSON or CSV:

![](http://media.charlesleifer.com/blog/photos/s1415487149.3.png)

The `import` tab supports importing CSV and JSON files into a table. There is an option to automatically create columns for any unrecognized keys in the import file:

![](http://media.charlesleifer.com/blog/photos/s1415479625.44.png)

### Command-line options

The syntax for invoking sqlite-web is:

```console

$ sqlite_web [options] /path/to/database-file.db
```

The following options are available:

* ``-p``, ``--port``: default is 8080
* ``-H``, ``--host``: default is 127.0.0.1
* ``-d``, ``--debug``: default is false
* ``-x``, ``--no-browser``: do not open a web-browser when sqlite-web starts.
* ``-P``, ``--password``: prompt for password to access sqlite-web.
  Alternatively, the password can be stored in the "SQLITE_WEB_PASSWORD"
  environment variable, in which case the application will not prompt for a
  password, but will use the value from the environment.
* ``-r``, ``--read-only``: open database in read-only mode.
* ``-u``, ``--url-prefix``: URL prefix for application, e.g. "/sqlite-web".
* ``-c``, ``--cert`` and ``-k``, ``--key`` - specify SSL cert and private key.
* ``-a``, ``--ad-hoc`` - run using an ad-hoc SSL context.

### Using docker

A Dockerfile is provided with sqlite-web. To use:

```console

$ cd docker/  # Change dirs to the dir containing Dockerfile
$ docker build -t coleifer/sqlite-web .
$ docker run -it --rm \
    -p 8080:8080 \
    -v /path/to/your-data:/data \
    -e SQLITE_DATABASE=db_filename.db \
    coleifer/sqlite-web
```
