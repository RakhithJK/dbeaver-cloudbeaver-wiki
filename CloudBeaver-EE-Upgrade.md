In order to upgrade wserver version you need to pull new image from Docker Hub and restart the server.

Before upgrading make sure you have a [[backup|CloudBeaver-Workspace-Backup]]. In some cases you wan't be able to downgrade if something will go wrong.

### Pull new server version

```sh
docker pull dbeaver/cloudbeaver-ee:${version.number}
docker restart ${containerId}
```

By default CloudBeaver EE container has name `cloudbeaver-ee` (for AWS server it is `cloudbeaver-aws`).  
If you use non-default run configuration then run `docker ps` to see all running containers and find you container (it is `dbeaver/cloudbeaver-ee:tag`).  

To upgrade to the latest version use `latest` as `${version.number}`. Otherwise specify the exact version number, e.g. `23.0.0`.   
