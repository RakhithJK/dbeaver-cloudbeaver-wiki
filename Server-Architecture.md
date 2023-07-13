## Overview

The CloudBeaver server is a Java application. It is based on the OSGI framework and utilizes several Eclipse bundles.
Back-end parts depend on [DBeaver](https://github.com/dbeaver/dbeaver). 
DBeaver is a multiplatform desktop application. It is also based on OSGI/Eclipse.  
Cloudbeaver uses a "headless" part of it - everything related to database connectivity and project management.

In order to build a CloudBeaver server you need to build DBeaver first. All DBeaver artefacts will be put in a local Maven repository so that CloudBeaver will see its dependencies. You can see `deploy/build.sh` script for details.

## Java

DBeaver relies on Java 11 language level and compile target.  
However, the default Java version is [OpenJDK 11](https://adoptopenjdk.net/?variant=openjdk11&jvmVariant=hotspot).
Maven 3.6+ is our default Java build system.  

## Libraries

- [Equinox](https://www.eclipse.org/equinox/) as OSGi container.
- [Eclipse Platform](https://www.eclipse.org/eclipse/) for virtual file system and plugin management.
- [Jetty](https://www.eclipse.org/jetty/) as a web server.
- [Java GraphQL](https://github.com/graphql-java/graphql-java) as a front-end communication API. 
- [DBeaver](https://github.com/dbeaver/dbeaver) as database management platform.
- Various 3rd party bundles with database drivers

## Supported databases

In the CloudBeaver Community we support only free and open-source databases. Such as:
- PostgreSQL
- MySQL
- MariaDB
- SQLite
- Firebird

We will add [more database drivers](https://github.com/dbeaver/cloudbeaver/wiki/Supported-databases)  support in future versions.
