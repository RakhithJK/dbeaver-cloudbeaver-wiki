## Intruduction

Cloudbeaver is a web server which provides rich web interface.  
It consists of two parts:
- Server back-end. It is writte on Java and reuses libraries of <a href="https://github/.com/dbeaver/dbeaver">.
- Front-end part. It is written on TypeScript and JavaScript.

This build process is relatively complicated (also consists of two parts).

### Prerequisites

* Java 11 (https://adoptopenjdk.net/?variant=openjdk11&jvmVariant=hotspot).
* Apache Maven (https://maven.apache.org/download.cgi)
* Node.js (https://nodejs.org/en/)
* Yarn (https://classic.yarnpkg.com/en/docs/install#windows-stable)

#### Install prerequisites on Ubuntu:
```sh
sudo apt update
sudo apt install openjdk-11-jdk
sudo apt install maven
sudo apt install cmdtest
sudo apt install nodejs
```

### Build and deploy

```sh
git clone https://github.com/dbeaver/cloudbeaver.git
cd cloudbeaver/deploy
./build.sh
```

Final artifacts can be found in deploy/cloudbeaver.

### Running server
```sh
cd cloudbeaver
./run-server.sh
```
By default server listens port `8978` (you can change it in conf/cloudbeaver.conf). So just navigate to http://localhost:8978.
You can configure nginx, Apache or any other web server in front of it.

