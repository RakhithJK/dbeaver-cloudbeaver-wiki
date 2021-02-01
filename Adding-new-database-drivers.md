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

Usually driver descriptions are located in DBeaver's `plugin.xml` files. You can search string `<driver` there and find a bunch of examples. 
Like this:
```xml
    <extension point="org.jkiss.dbeaver.dataSourceProvider">
        <datasource id="postgresql" label="PostgreSQL" ...>
            ....

            <drivers managable="true">
                ...
                <driver
                    id="postgres-jdbc"
                    label="PostgreSQL"
                    icon="icons/postgresql_icon.png"
                    iconBig="icons/postgresql_icon_big.png"
                    class="org.postgresql.Driver"
                    sampleURL="jdbc:postgresql://{host}[:{port}]/[{database}]"
                    useURL="true"
                    defaultPort="5432"
                    defaultDatabase="postgres"
                    defaultUser="postgres"
                    webURL="https://jdbc.postgresql.org/"
                    propertiesURL="https://jdbc.postgresql.org/documentation/head/connect.html#connection-parameters"
                    description="%driver.postgresql.description"
                    categories="sql">
                    <file type="jar" path="maven:/org.postgresql:postgresql:RELEASE[42.2.5]">
                    <file type="jar" path="maven:/net.postgis:postgis-jdbc:RELEASE[2.2.1]" ignore-dependencies="true" optional="true"/>
                    <file type="jar" path="maven:/net.postgis:postgis-geometry:RELEASE[2.5.0]" ignore-dependencies="true" optional="true"/>

                    <parameter name="serverType" value="postgresql"/>
                    <property name="loginTimeout" value="20"/>
                    <property name="connectTimeout" value="20"/>
                </driver>
                ...
            </drivers>
        </datasource>
    </extension>
```
It is actual PostgreSQL driver definition (irrelevant configuration elements were skipped).  
Full driver ID is `postgresql.postgres-jdbc`. It is combined from two parts: data source provider ID and driver definition ID.   
Note: for most non-standard driver you must add new driver definition to Generic plugin (`org.jkiss.dbeaver.ext.generic`) because it works with plain JDBC API only.

### Adding driver definition in UI.

Custom drivers configuration in UI is described in the [[Database Drivers|https://github.com/dbeaver/dbeaver/wiki/Database-drivers]] article.  
After that you can find you driver definition in the `drivers.xml` (see [[Administering drivers|https://github.com/dbeaver/dbeaver/wiki/Admin-Manage-Drivers]]). Then you can copy it into the appropriate plugin.xml file.

## Maven

