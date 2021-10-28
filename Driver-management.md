CloudBeaver supports almost any database which has a JDBC driver.  
It generally supports all drivers supported by DBeaver.  

By default, do not enable all DBeaver drivers in CloudBeaver. They must be added to the server configuration on demand.  

#### Adding new driver dependencies

Driver dependencies are configured in the folder `server/drivers`.  
In order to add a new driver: 
- Create new folder for a new driver
- Copy the POM file from any another driver config to the new directory
- Change the module name and driver dependencies in the new POM file

Example of PostgreSQL driver config:
```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
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
        <deps.output.dir>postgresql</deps.output.dir>
    </properties>

    <dependencies>
        <dependency>
            <groupId>org.postgresql</groupId>
            <artifactId>postgresql</artifactId>
            <version>42.2.20</version>
        </dependency>
        <dependency>
            <groupId>net.postgis</groupId>
            <artifactId>postgis-jdbc</artifactId>
            <version>2.5.0</version>
        </dependency>
    </dependencies>

</project>
```

#### Adding a new driver to the server

Enabled drivers are configured in the file, `server/bundles/io.cloudbeaver.resources.drivers.base/plugin.xml`.  
You can copy an existing driver configuration to add a new one.

There are 3 configuration lines for each driver:
1. `<resource name="drivers/driver-name"/>` - says that the file-system folder `drivers/driver-name` can be used to load driver jars.
1. `<bundle id="drivers.driver-name"/>` - needed for driver configuration enable in the DBeaver platform
1. `<driver id="generic:driver-name"/>` - enabled the DBeaver driver in CloudBeaver. The driver ID can be found in the DBeaver platform (in one of the database-specific `plugin.xml` files).

