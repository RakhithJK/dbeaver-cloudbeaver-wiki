CloudBeaver supports many popular databases out of the box.  
But sometimes you need to add a new driver - less popular than a custom driver developed by your company.  

This instruction describes how you can do it.

## Introduction

CB is based on the [[DBeaver |https://github.com/dbeaver/dbeaver]] platform. It reuses drivers provided by DBeaver plugins.  
Thus, you can not add a driver which is not configured in some DBeaver plugins.

Out of the box DBeaver supports more than 50 different database drivers. Some of them are pre-configured in CloudBeaver as well, and some are not.  
Generally, adding a new driver in CB consists of two steps:
1. Add driver in DBeaver
2. Configure this driver in CloudBeaver

If a driver is already included in DBeaver, then you can skip the first step. 

### What is special about CloudBeaver compared to DBeaver?

DBeaver downloads database drivers (JDBC) on demand (after the first attempt to connect to the database). This approach does not work in CloudBeaver, mostly because the driver download may require some user interactions + access to external resources + some local file system permissions.  
CloudBeaver must have all driver jars pre-downloaded in the folder set as `driversLocation` in the [[Server configuration]].  By default it is a directory `drivers` in the root of CloudBeaver deployment.

## Configuring drivers in DBeaver

The driver descriptions are usually located in the DBeaver's `plugin.xml` files. You can search the string `<driver` there and find a bunch of examples. 
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
                    <file type="jar" path="maven:/org.postgresql:postgresql:RELEASE[42.2.20]" bundle="!drivers.postgresql"/>
                    <file type="jar" path="drivers/postgresql" bundle="drivers.postgresql"/>

                    <parameter name="serverType" value="postgresql"/>
                    <property name="loginTimeout" value="20"/>
                    <property name="connectTimeout" value="20"/>
                </driver>
                ...
            </drivers>
        </datasource>
    </extension>
```
It is the actual PostgreSQL driver definition (irrelevant configuration elements were skipped).  
The full driver ID is `postgresql.postgres-jdbc`. It is made up of two parts: the data source provider ID and the driver definition ID.   

Note: for most non-standard drivers you must add a new driver definition to the Generic plugin (`org.jkiss.dbeaver.ext.generic`) because it only works with plain JDBC API.

### Adding driver definition in UI (optional).

You can add a new driver configuration manually in the plugin.xml. But you can also generate this configuration in the DBeaver user interface.  

Adding custom drivers configuration in the UI is described here: [[Database Drivers|https://github.com/dbeaver/dbeaver/wiki/Database-drivers]].  
After that you can find you driver definition in the `drivers.xml` (see [[Administering drivers|https://github.com/dbeaver/dbeaver/wiki/Admin-Manage-Drivers]]). Then you can copy it into the appropriate plugin.xml file.

### Maven

All drivers need some 3rd party jar files (actual driver executable code).  
For CloudBeaver 3rd party jars must be in a public Maven repository (Maven Central is preferred). Line
```xml
<file type="jar" path="maven:/org.postgresql:postgresql:RELEASE[42.2.20]">
```
refers to external Maven artifact which must contain driver jar files.

### Drivers and bundles

In the driver definition example (see above) you can see two lines: 
```xml
<file type="jar" path="maven:/org.postgresql:postgresql:RELEASE[42.2.20]" bundle="!drivers.postgresql"/>
<file type="jar" path="drivers/postgresql" bundle="drivers.postgresql"/>
```
The first one refers to the actual Maven artifact. The Second one refers to some weird path `drivers/postgresql`. What does it mean?  
The DBeaver Community does not contain any drivers' jars. It downloads them on demand. But DBeaver EE and CloudBeaver and other products may contain drivers out of the box so users will not need to download them.  
These two lines configure the driver for these two different situations. If you do not plan to include your driver configuration in DBeaver, then you may skip the first line.

### Testing and contributing (optional)

After you add your new driver in plugin.xml you must be able to connect to your database in DBeaver UI by choosing your new driver in the new connection wizard:
- Build the DBeaver desktop app (run `mvn clean package` in the root folder).
- Run dbeaver executable in product/standalone/target/products/.../dbeaver folder (path differs for different OSes).
- Open the "New Connection" wizard. Configure your connection and click the "Test Connection" button.

If everything is fine then you can create a Pull Request and contribute your changes in the main DBeaver repository. This part is optional, you can leave everything in your local version or your forked version of DBeaver. In this case you will need to fix the CloudBeaver build script (default build script uses the main dbeaver repository as a platform source code).

## Adding drivers in CloudBeaver

You need to configure the driver in CloudBeaver separately. Because it does not include all existing drivers from DBeaver.

### Adding Maven artifact(s)

You must include a driver in the server build. All 3rd party jars must be available for the server during the startup. By default, the CB buidl script downloads 3rd party jars from Maven Central but you can add a custom logic there.

- Explore directory [[server/drivers|https://github.com/dbeaver/cloudbeaver/tree/devel/server/drivers]].  
- Create a new sub-folder `new-driver-id`. You can copy-paste some existing driver directory for simplification.
- Add `pom.xml` file in the new directory. It is a standard Maven pom. It can look like this:
```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <artifactId>drivers.postgresql</artifactId>
    <version>1.0.0</version>
    <parent>
        <groupId>io.cloudbeaver</groupId>
        <artifactId>drivers</artifactId>
        <version>1.0.0</version>
        <relativePath>../</relativePath>
    </parent>
    <properties>
        <deps.output.dir>new-driver-id</deps.output.dir>
    </properties>
    <dependencies>
        <dependency>
            <groupId>new.driver.vendor/groupId>
            <artifactId>new-driver-artifact.id</artifactId>
            <version>new-driver-artifact-version</version>
        </dependency>
    </dependencies>
</project>
```
- Add you new driver id (equals to the new directory name) to the main [[server/drivers/pom.xml|https://github.com/dbeaver/cloudbeaver/blob/devel/server/drivers/pom.xml]] in the `<modules>` section.  

### Include driver in server configuration

- Open file [[server/bundles/io.cloudbeaver.resources.drivers.base/plugin.xml|https://github.com/dbeaver/cloudbeaver/blob/devel/server/bundles/io.cloudbeaver.resources.drivers.base/plugin.xml]]
- Add line `<resource name="drivers/new-driver-id"/>` in the end of other resource references. It will tell CloudBeaver where to find your new driver's jars.
- Add line `<bundle id="drivers.new-driver-id" label="New driver files"/>` in the end of bundle list. See <a href="#Drivers-and-bundles">bundle configuration description</a> for explanation.
- Add line `<driver id="full-driver-id"/>` in the end of the enabled drivers list. Usually, your full driver id will be something like `generic.new-driver-id`.

That's it.

## Deploy and test

See [[Build and deploy|https://github.com/dbeaver/cloudbeaver/wiki/Build-and-deploy]]. Then just run the `deploy.sh` script in the `deploy` folder. You will get your brand new driver included in the CloudBeaver server configuration.  
Start the server. Examine log files - if something went wrong, you will see warnings or error messages in the server log.  
