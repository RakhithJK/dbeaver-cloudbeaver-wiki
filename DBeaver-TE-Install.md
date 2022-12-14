This instructin explain how to configure and deploy DBeaver Team Edition.  
It is supposed to be read by system administrators and/or devops engineers.  

DBeaver Team Edition consists of the following components:
- CloudBeaver Team server (installed on server side)
- DBeaverTeam desktop clients (installed on multiple client machines)

### CloudBeaver Team Edition Server installation

CloudBeaver TE consists of multiple docker containers.  
We created a special GitHub repository with instructions and configuration: https://github.com/dbeaver/team-edition-deploy  
Run command `git clone https://github.com/dbeaver/team-edition-deploy.git` in console before deployment.  

There are two ways to run docker container:
- [docker-compose](https://github.com/dbeaver/team-edition-deploy/compose/cbte)
- [Kubernetes](https://github.com/dbeaver/team-edition-deploy/k8s/cbte)

### DBeaver Team client installation

You can download DBeaver Team client from https://dbeaver.com/download/team-edition/

After installation you need to configure desktop client to connect to your previously deployed CloudBeaver Team Edition server.
