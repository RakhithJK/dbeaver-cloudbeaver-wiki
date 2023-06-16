


**Team Edition** is the most comprehensive DBeaver product for effective team collaboration which consists of three parts:


1. **Server cluster** that allows you to store all the connection settings, scripts, diagrams, and other objects, as well as immediately get the latest updates from your colleagues' editing


2. Web-based **Team Edition CloudBeaver** application which is similar to the CloudBeaver Enterprise Edition

3. Desktop **Team Edition DBeaver** application which is similar to the DBeaver Ultimate Edition 

_Please refer to DBeaver products description for more [details](https://dbeaver.com/edition/)_



To start working with Team Edition, go through the following steps:

1. Server cluster deployment. At this step, decide whether it will be _**Docker Compose**_ or _**Kubernetes**_. Detailed instructions for these methods can be found [here](https://github.com/dbeaver/team-edition-deploy/). If you want another technology to run containers and need assistance, please inform us in our [online technical support system](https://dbeaver.com/support/).  We managed to successfully set up _**ECS + Fargate + EFS**_, _**OpenShift**_, and other services.

2. Team Edition CloudBeaver setup in the browser. Here you need to switch to the browser. 

For _**Docker Compose**_:

In the adrress bar, type the URL configured in the **_.env_** file. For example, for the: 


`CLOUDBEAVER_DOMAIN=localhost`


`CLOUDBEAVER_SCHEME=http`



specified in the ___.env___ file


use the `http://localhost` in the address bar:



![TECBEE](https://github.com/dbeaver/cloudbeaver/assets/49681450/54cb9124-7d90-4aa9-9b2e-349fe80f8556)

Use the default credentials to login:

**User name**: `cbadmin`
**User password**: `cbadmin20`

After that, you will be prompted to insert your license:

![TECBEE1](https://github.com/dbeaver/cloudbeaver/assets/49681450/20d045e4-b5ec-4593-9c9e-247871503918)

Continue Team Edition DBeaver configuration using the [tabs](https://github.com/dbeaver/cloudbeaver/wiki/DBeaver-TE-Configuration) in the administration panel. 

3. Setting up Team Edition DBeaver desktop client.

Download the installation files from the [website](https://dbeaver.com/download/team-edition/).

When you run Team Edition DBeaver for the first time, enter the domain controller URL. It is **the same** as the URL you enter in **step 2** in the address bar to access Team Edition CloudBeaver:




![TEDB](https://github.com/dbeaver/cloudbeaver/assets/49681450/fdaed67c-7b2f-4bc8-9b36-d70e6b45d67b)


Login with the default **User name** and **User password**:

![TEDB1](https://github.com/dbeaver/cloudbeaver/assets/49681450/56b334b4-b257-496f-ac65-2eecd6fabf87)


You will be able to login using the preferred authentication mechanisms afterward.

