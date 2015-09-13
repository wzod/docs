# CRITs

This is the documentation page for the Collaborative Research Into Threats (CRITs) Docker image, which is available in the REMnux DockerHub repository.

CRITs is a web-based tool which combines an analytic engine with a cyber threat database that not only serves as a repository for attack data and malware, but also provides analysts with a powerful platform for conducting malware analyses, correlating malware, and for targeting data. (reference: https://github.com/crits/crits/blob/master/README.md)

The CRITs docker image provides a fully functional instance of CRITs including an Apache web server, Mongo database and Supervisord to manage services. The Docker image allows for easy instantiation and also offers a means for retaining CRITS data, indefinitely.

##Category

Knowledge Management System

##Usage

    sudo docker run [OPTIONS] IMAGE [COMMAND] [ARG...]

Options:
   * `--rm`        Automatically remove the container when it exits (incompatible with -d)
   * `-i`          Keep stdin open even if not attached
   * `-t`          Allocate a pseudo-tty
   * `-v`          Bind mount a volume (e.g. from the host: -v /host:/container, from docker: -v /container)
   * `-p`          Publish a container's port to the host (format: ip:hostPort:containerPort | ip::containerPort | hostPort:containerPort)

##Example

    sudo docker run --rm -it -v ~/crits-data:/home/nonroot/workdir -p 8443:8443 remnux/crits

Before running the Docker image, create the ~/crits-data directory on the host system and make it world-accessible:

    mkdir -pv ~/crits-data
    chmod a+xwr ~/crits-data

Once the Docker image is loaded and CRITs is fully instantiated, access the CRITs web interface by entering the following into a web browser:

    https://localhost:8443

To access the CRITs web application, enter the username "nonroot" and supply the temporary password that is presented when the Docker image completes initialization.

__Please change the temporary password upon successful login to the web interface by clicking on 'Nonroot User' near the top left panel and selecting 'Change Password'.__

If changes made to the CRITs application require a restart of the web server, run the following command from within the Docker instance:

    service apache2 stop

As soon as the apache2 service is stopped, supervisord will automatically restart the web server and the changes made to the CRITs application will be applied, automatically.

To ensure data persists after making changes to the CRITs Docker instance, logout of the web application and copy the database directory to the working directory (i.e. /home/nonroot/workdir/) from within the Docker container like so (the same can be done for the /data/log directory should there be a need to retain log data):

    nonroot@a8cdeb7e0a1c:/data/crits$ cp -r /data/db ~/workdir/

The above command will copy data to the ~/crits-data directory on the host system. If/when the Docker image is exited, simply copy the database directory from the host system to the database directory while running the Docker instance after the Docker image completes initialization like so:

    nonroot@d5678e7641ad:/data/crits$ cp -r ~/workdir/db/* /data/db/

##References

* https://crits.github.io/
* https://github.com/crits/crits
* https://github.com/crits/crits/wiki

##Author and Source

* [@wzod](https://twitter.com/wzod)
* https://github.com/wzod/Dockerfiles/blob/master/CRITs/Dockerfile

## Location on REMnux

CRITs is available in the REMnux DockerHub, https://hub.docker.com/r/remnux/crits/
