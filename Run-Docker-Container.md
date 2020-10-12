CloudBeaver container image is on DockerHub: https://hub.docker.com/r/dbeaver/cloudbeaver.  
- `dbeaver/cloudbeaver:latest` - latest release build.
- `dbeaver/cloudbeaver:dev` - latest developer build.

#### Installation 
To install the latest version of CloudBeaver use the following script:

```sh
sudo docker pull dbeaver/cloudbeaver:latest
```

#### Running 

To run cloudbaver in terminal:
```sh
sudo docker run --name cloudbeaver --rm -ti -p 80:8978 -v /var/cloudbeaver/workspace:/opt/cloudbeaver/workspace dbeaver/cloudbeaver:latest
```

Then switch to the browser and open http://localhost:8978/

Details:
Parameter | Explanation
---|---
--name cloudbeaver | Assign container ID (`cloudbeaver`)
--rm | Removes container on stop
-ti | Enables terminal mode (allows to stop container with `CTRL+C`)
-p 80:8978 | Maps CloudBeaver public port (8978) to the host machine port (e.g. 80, default HTTP port)
-v local_path:/opt/cloudbeaver/workspace | Mounts local folder `/var/cloudbeaver/workspace' to the server workspace. Required to keep CloudBeaver data after container restart.
dbeaver/cloudbeaver:latest | Container ID

#### Daemon mode

Add following parameters:
```
-d --restart unless-stopped 
```

#### Accessing databases on the localhost

If you need to access database server on the host machine add the following parameter in docker run: (on Linux only)
```
 --network host
```
