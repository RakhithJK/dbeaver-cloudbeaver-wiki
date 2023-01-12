CloudBeaver container image is on DockerHub: https://hub.docker.com/r/dbeaver/cloudbeaver.  
- `dbeaver/cloudbeaver:latest` - latest release build.
- `dbeaver/cloudbeaver:dev` - latest developer build.

#### Installation 
To install the latest version of CloudBeaver use the following script:

```sh
sudo docker pull dbeaver/cloudbeaver:latest
```

#### Running 

To run cloudbaver in the terminal:
```
sudo docker run --name cloudbeaver --rm -ti -p 8080:8978 -v /var/cloudbeaver/workspace:/opt/cloudbeaver/workspace dbeaver/cloudbeaver:latest
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

docker run --name cloudbeaver --rm -ti -p 8080:8978 --add-host=host.docker.internal:${CB_LOCAL_HOST_ADDR} -v /var/cloudbeaver/workspace:/opt/cloudbeaver/workspace dbeaver/cloudbeaver:dev
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
dbeaver/cloudbeaver:latest | Container ID


### Run Cloudbeaver server with non-root user

before container starts you must build your own image with an user inside.
Create **Dockerfile** which contains:
```
FROM dbeaver/cloudbeaver:latest
RUN groupadd cloudbeaver
RUN useradd -ms /bin/bash -g cloudbeaver cloudbeaver
RUN chown -R cloudbeaver ./
USER cloudbeaver
```

Now run this command to build image from **Dockerfile**
```
docker build -t my-cloudbeaver .
```

To run cloudbaver in the terminal:
```
sudo docker run --name cloudbeaver --rm -ti -p 8080:8978 -v /var/cloudbeaver/workspace:/opt/cloudbeaver/workspace my-cloudbeaver
```