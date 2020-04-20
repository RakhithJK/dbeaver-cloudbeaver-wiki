## Build

### Prerequisites

* Java 8, 9, 10, 11 or 12
* Apache Maven
* Node.js
* Yarn

### Build and deploy
```
git clone https://github.com/dbeaver/cloudbeaver.git
cd cloudbeaver/deploy
./build.sh
```

Final artifacts can be found in deploy/cloudbeaver.

### Running server
```
cd cloudbeaver
./run-server.sh
```
By default server listens port 8978 (you can change it in conf/cloudbeaver.conf). You can configure nginx, Apache or any other web server in front of it.

