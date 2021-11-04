## AWS Marketplace

You can subscribe to CloudBeaver EE in the AWS Marketplace here: https://aws.amazon.com/marketplace/pp/B08QTY2JTF.  

There is a one month trial period.  

## IAM/EC2 installation

After launching EC2 instance based on CloudBeaver IAM, open the page `http:://EE2_IP/` where `EE2_IP` is the IP address of your new EC2 machine.  
On the first page you will see [[server configuration wizard|Administration]].  

You can connect to your EC2 instance using SSH. You need to specify the SSH keypair during the EC2 instance launch. You can use the user name `ubuntu` to connect.  

## Docker image

Not yet supported. We are working on the new docker image for the AWS version of CloudBeaver.  

## Cloud explorer

You can use an embedded cloud explorer in order to find and add existing AWS databases:

![](images/aws-explorer.png)