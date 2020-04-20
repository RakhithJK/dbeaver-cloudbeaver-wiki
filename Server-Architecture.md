## Overview

Cloudbeaver server is a Java application. It is based on OSGI framework and utilizes several Eclipse bundles.
Back-end parts depends on [DBeaver](https://github.com/dbeaver/dbeaver). 
DBeaver is a multiplatform desktop application. It also based on OSGI/Eclipse.  
Cloudbeaver uses "headless" part of it - everything related to database connectivity and project management.

Anyway, in order to build cloudbeaver server you need to build dbeaver first. All dbeaver artifacts will be put in local Maven repository so cloudbeaver will see its dependencies. You can see `deploy/build.sh` script for details.

## Libraries

- [Jetty](https://www.eclipse.org/jetty/) as a web server.
- [Java GraphQL](https://github.com/graphql-java/graphql-java) as a front-end communication API