## AWS Marketplace

You can subscribe to CloudBeaver EE in the AWS Marketplace here: https://aws.amazon.com/marketplace/pp/B08QTY2JTF.  

There is a one month trial period.  

## IAM/EC2 installation

After launching EC2 instance based on CloudBeaver IAM, open the page `http://EE2_IP/` where `EE2_IP` is the IP address of your new EC2 machine.  
On the first page you will see [[server configuration wizard|Administration]].  

You can connect to your EC2 instance using SSH. You need to specify the SSH keypair during the EC2 instance launch. You can use the user name `ubuntu` to connect.  

## Docker image

Besides AWS marketplace you can run CloudBeaver AWS from docker image.  
In this case you will need specify a license during product configuration. A license can be purchased on https://cloudbeaver.io website.  

Docker images:
dbeaver/cloudbeaver-aws:latest - latest release build.
dbeaver/cloudbeaver-aws:dev - latest developer build.
dbeaver/cloudbeaver-aws:[version] - image of exact version of CloudBeaver AWS.  

To install just run command:
```sh
sudo docker pull dbeaver/cloudbeaver:latest
```

To run cloudbaver in the terminal:
```
sudo docker run --name cloudbeaver --rm -ti -p 8080:8978 -v /var/cloudbeaver/workspace:/opt/cloudbeaver/workspace dbeaver/cloudbeaver:latest
```

## Cloud explorer

You can use an embedded [[Cloud explorer|AWS-Cloud-explorer]] in order to find and add existing AWS databases:

![](images/aws-explorer.png)