CloudBeaver supports many popular databases out of the box.  
But sometimes you need to add a new driver - less popular of even some custom driver developed inside your company.  

This instruction describes how you can do it.

## Introduction

CB is based on [[DBeaver |https://github.com/dbeaver/dbeaver]] platform. It reuses drivers provided by DBeaver plugins.  
Thus you can not add a driver which is not configured in some of DBeaver plugins.

Out of the box DBeaver supports more than 50 different database drivers. Some of them pre-configured in CloudBeaver as well, some are not.  
Generally adding new driver in CB consists of two steps:
1. Add driver in DBeaver
2. Configure this driver in CloudBeaver

If driver already included in DBeaver then you can skip the first step. 

### What is special about CloudBeaver comparing to DBeaver?

DBeaver downloads database drivers (JDBC) on demand (on first attempt to connect to the database). This approach doesn't work in case of CloudBeaver. Mostly because driver download may require some user interactions + access to external resources + some local file system permissions.  
CloudBeaver must have all driver jars pre-downloaded in the folder set as `driversLocation` in the [[Server configuration]].  By default is is a directory `drivers` in the root of CloudBeaver deployment.

## Configuring drivers in DBeaver



## Maven

