Build and run
-------------

Build the docker image:
$ docker build -t dockertest.web .

See all local images:
$ docker images

Create and start a container named dockertest.web from image called dockertest.web, mapping port 8080 on localhost to port 80 on the container:
$ docker run -d -p 8080:80 --name dockertest.web dockertest.web

Open http://localhost:8080 in a browswer!


Troubleshooting
---------------

If you get this error message:
Error response from daemon: driver failed programming external connectivity on endpoint dockertest.web (5897c361283d5cdc412a12454fb8269340129557b2a64ee3ca55d0d8c357bd42): Error starting userland proxy: mkdir /port/tcp:0.0.0.0:8080:tcp:172.17.0.2:5000: input/output error.
You need to restart docker by right-clicking the docker icon in the system tray and select "Restart..."
See https://github.com/docker/for-win/issues/573 for more info

To see listening ports in a container:
$ docker exec dockertest.web ss -l
`ss` is a more advanced replacement for `netstat`
