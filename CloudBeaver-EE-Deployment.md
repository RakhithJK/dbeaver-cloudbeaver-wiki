CloudBeaver EE container image is on DockerHub: https://hub.docker.com/r/dbeaver/cloudbeaver-ee.  
- `dbeaver/cloudbeaver-ee:latest` - latest release build.
- `dbeaver/cloudbeaver:x.y.z` - particular product version.

It is a public repository so you can just pull it.  

#### Installation 
To install the latest version of CloudBeaver EE use the following script:

```sh
sudo docker pull dbeaver/cloudbeaver-ee:latest
```

#### Running 

To run cloudbaver in terminal:
```
sudo docker run --name cloudbeaver-ee --rm -ti -p 8080:8978 -v /var/cloudbeaver-ee/workspace:/opt/cloudbeaver/workspace dbeaver/cloudbeaver-ee:latest
```

Then switch to the browser and open http://localhost:8080/

To run server in daemon mode add following parameters:
```
-d --restart unless-stopped 
```

### Accessing databases on the localhost

If you need to access database server on the host machine add the following parameter in docker run: (on Linux only)
```
 --network host
```

Thus cloudbeaver will work in host machine network.  
If this mode is not suitable for your network environment then you can run container the following way:
```
export CB_LOCAL_HOST_ADDR=$(ifconfig | grep -E "([0-9]{1,3}\.){3}[0-9]{1,3}" | grep -v 127.0.0.1 | awk '{ print $2 }' | cut -f2 -d: | head -n1)

docker run --name cloudbeaver-ee -d --restart unless-stopped -ti -p 8080:8978 --add-host=host.docker.internal:${CB_LOCAL_HOST_ADDR} -v /var/cloudbeaver-ee/workspace:/opt/cloudbeaver/workspace dbeaver/cloudbeaver-ee:latest
```
or just run script `deploy/docker/run-docker-container.sh`.
It passes IP address of host machine to the container.

### Docker parameters explanation

Parameters explanation:

Parameter | Explanation
---|---
--name cloudbeaver-ee | Assign container ID (`cloudbeaver-ee`)
--rm | Removes container on stop
-ti | Enables terminal mode (allows to stop container with `CTRL+C`)
-p 8080:8978 | Maps CloudBeaver public port (8978) to the host machine port (e.g. 8080)
-v local_path:/opt/cloudbeaver-ee/workspace | Mounts local folder `/var/cloudbeaver-ee/workspace' to the server workspace. Required to keep CloudBeaver EE data after container restart.
--add-host=host.docker.internal:IP address | Adds host name in the container's /etc/hosts file. This may be needed to access database server deployed on the host machine.
dbeaver/cloudbeaver-ee:latest | Container ID
