This instruction explains how to configure and deploy DBeaver Team Edition.  
It is supposed to be read by system administrators and/or devops engineers.  

DBeaver Team Edition consists of the following components:
- CloudBeaver Team server (installed on server side)
- DBeaverTeam desktop clients (installed on multiple client machines)

### CloudBeaver Team Edition Server installation

CloudBeaver TE consists of multiple docker containers.  
We created a special GitHub repository with instructions and configuration: https://github.com/dbeaver/team-edition-deploy  
Run command `git clone https://github.com/dbeaver/team-edition-deploy.git` in console before deployment.  

There are two ways to run docker container:
- [docker-compose](https://github.com/dbeaver/team-edition-deploy/tree/devel/compose)
- [Kubernetes](https://github.com/dbeaver/team-edition-deploy/tree/devel/k8s)

### DBeaver Team client installation

You can download DBeaver Team client from https://dbeaver.com/download/team-edition/

After installation you need to configure desktop client to connect to your previously deployed CloudBeaver Team Edition server.

By default DBeaver Team will try to detect server automatically by getting value from:
- Environment variable `DBEAVER_DOMAIN_CONTROLLER`
- Init parameter `DBEAVER_DOMAIN_CONTROLLER` (it can be set in dbeaver.ini file by adding line `-DDBEAVER_DOMAIN_CONTROLLER=URL` at the end
- Windows registry key `HKEY_CURRENT_USER\Software\DBeaverTeam\DomainControllerURL`
- Windows registry key `HKEY_LOCAL_MACHINE\Software\DBeaverTeam\DomainControllerURL`

If none of these methods will succeeed (default behavior) then it will ask for DC URL in popup dialog.
After that passed URL will be saved in file `%APPDATA%\DBeaverData\team-workspace\.metadata\domain-controller.properties`. You can change saved value in this file manually later.

