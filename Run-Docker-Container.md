### Docker repositories

CloudBeaver container images are on DockerHub: 

Product | Docker repository | URL
---|---|---
CloudBeaver EE | dbeaver/cloudbeaver-ee | https://hub.docker.com/r/dbeaver/cloudbeaver-ee  
CloudBeaver AWS | dbeaver/cloudbeaver-aws | https://hub.docker.com/r/dbeaver/cloudbeaver-aws
CloudBeaver Community | dbeaver/cloudbeaver | https://hub.docker.com/r/dbeaver/cloudbeaver

Each image has following tags:

Tag | Description
---|---
latest | The latest stable product release
22.1.2, 23.0.1, etc | Exact product version
ea | Early Accesss version
devel | Development version, unstable

Examples:

- `dbeaver/cloudbeaver-ee:23.0.0` - CloudBeaver EE version 23.0
- `dbeaver/cloudbeaver-aws:ea` - CloudBeaver AWS Early Access version
- `dbeaver/cloudbeaver:latest` - latest community release

Notes:
- We will use repository `cloudbeaver-ee` as an example in the following instructions. Replace it with proper product repository (see above).  
- To run docker commands your user must be in proper user group or run it as root (e.g. `sudo docker ps`).

#### Installation 

To install the latest version of CloudBeaver use the following script:

```sh
docker pull dbeaver/cloudbeaver-ee:latest
```

#### Running 

To run cloudbaver in the terminal:
```
docker run --name cloudbeaver-ee --rm -ti -p 8080:8978 -v /var/cloudbeaver/workspace:/opt/cloudbeaver/workspace dbeaver/cloudbeaver-ee:latest
```

Then switch to the browser and open http://localhost:8080/

#### Daemon mode

Add the following parameters:
```
-d --restart unless-stopped 
```

### Accessing databases on the localhost

If you need to access the database server on the host machine, add the following parameter in docker run: (on Linux only)
```
 --network host
```

Cloudbeaver will work in the host machine network.  
If this mode is not suitable for your network environment then you can run the container in the following way:
```
export CB_LOCAL_HOST_ADDR=$(ifconfig | grep -E "([0-9]{1,3}\.){3}[0-9]{1,3}" | grep -v 127.0.0.1 | awk '{ print $2 }' | cut -f2 -d: | head -n1)

docker run --name cloudbeaver --rm -ti -p 8080:8978 --add-host=host.docker.internal:${CB_LOCAL_HOST_ADDR} -v /var/cloudbeaver/workspace:/opt/cloudbeaver/workspace dbeaver/cloudbeaver-ee:latest
```
or just run script `deploy/docker/run-docker-container.sh`.
It passes the IP address of host machine to the container.

### Docker parameters explanation

Parameters explanation:

Parameter | Explanation
---|---
--name cloudbeaver | Assign container ID (`cloudbeaver`)
--rm | Removes container on stop
-ti | Enables terminal mode (allows to stop container with `CTRL+C`)
-p 8080:8978 | Maps CloudBeaver public port (8978) to the host machine port (e.g. 8080)
-v local_path:/opt/cloudbeaver/workspace | Mounts local folder `/var/cloudbeaver/workspace' to the server workspace. Required to keep CloudBeaver data after container restart.
--add-host=host.docker.internal:IP address | Adds host name in the container's /etc/hosts file. This may be needed to access the database server deployed on the host machine.
dbeaver/cloudbeaver-ee:latest | Container ID


### Run Cloudbeaver server with non-root user

If you want to run CloudBeaver with a non-root user, you have to build your own image with a user inside before the container starts.

Create **Dockerfile** which contains:
```
FROM dbeaver/cloudbeaver-ee:latest
RUN groupadd cloudbeaver
RUN useradd -ms /bin/bash -g cloudbeaver cloudbeaver
RUN chown -R cloudbeaver ./
USER cloudbeaver
```

Run this command to build the image from **Dockerfile**
```
docker build -t my-cloudbeaver .
```

To run CloudBeaver in the terminal:
```
docker run --name cloudbeaver --rm -ti -p 8080:8978 -v /var/cloudbeaver/workspace:/opt/cloudbeaver/workspace my-cloudbeaver
```


### Offline install

On a host with no internet access you need to download and archve image:

Note: `<TAG>` is a tag name for docker image (see above). `latest` is the default.  
```
docker pull dbeaver/cloudbeaver-ee:<TAG>
docker save dbeaver/cloudbeaver-ee:<TAG> | gzip > cloudbeaver-ee.latest.tar.gz
```

Check that the archive exist:
```
ls -lah
```

Output should looks like:
```
-rw-r--r-- 1 user users 444M may 5 17:32 cloudbeaver-ee.latest.tar.gz
```

Now copy file `cloudbeaver-ee.latest.tar.gz` to some external drive and put to server with running cloudbeaver server.

Load image from archve:
```
docker load < cloudbeaver-ee.latest.tar.gz
```
You will see next output
```
Loaded image: dbeaver/cloudbeaver-ee:<TAG>
```

Upgrade your cloudbeaver-ee server:
```
docker stop cloudbeaver-ee
docker rm cloudbeaver-ee
docker run -d --restart unless-stopped -p 8978:8978 -v /var/cloudbeaver-ee/workspace:/opt/cloudbeaver/workspace dbeaver/cloudbeaver-ee:<TAG>
```
Note: some of docker args may differ from your environment.
