## Introduction

CloudBeaver is a web server which provides a rich web interface.  
It consists of two parts:
- Server back-end. It is written in Java and reuses "platform" libraries of <a href="https://github/.com/dbeaver/dbeaver">DBeaver</a>.
- Front-end part. It is written in TypeScript and JavaScript.

This build process is relatively complicated (and also consists of two parts).

### Prerequisites

- [Java 17](https://adoptium.net/)
- [Apache Maven (3.8.6+)](https://maven.apache.org/download.cgi)
- [Node.js (16.x)](https://nodejs.org/en/)
- [Yarn](https://classic.yarnpkg.com/en/docs/install#windows-stable) (1.22.x)
- [NPM](https://www.npmjs.com/get-npm) + [Lerna](https://www.npmjs.com/package/lerna)

#### Install prerequisites on Ubuntu:

Add Node.js (version 16.x minimal version 16.18) and Yarn 1.22.x version repo:
```bash
  curl -sL https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
  echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
  curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
```
Install packages:
```bash
sudo apt update
sudo apt install openjdk-17-jdk
sudo apt install maven
sudo apt install yarn
sudo apt install nodejs
sudo apt install npm
```

#### Install prerequisites on Windows:

- Download and install [AdoptOpenJDK](https://adoptopenjdk.net/?variant=openjdk17&jvmVariant=hotspot)
- Download and extract [Maven](https://maven.apache.org/download.cgi). 
- Add path to Maven bin folder in system PATH
- Download and install [Node.js](https://nodejs.org/en/). NPM comes along with Node.js, NPX/Lerna will be installed in the build script.
- Download and install [Yarn](https://classic.yarnpkg.com/en/docs/install#windows-stable) 1.22.x

### Build and deploy

```bash
git clone https://github.com/dbeaver/cloudbeaver.git
cd cloudbeaver/deploy
./build.sh
```

The final artifacts can be found in `deploy/cloudbeaver`.

### Running server
```bash
cd cloudbeaver
./run-server.sh
```
By default, the server listens to port `8978` (you can change it in conf/cloudbeaver.conf). So just navigate to http://localhost:8978.
You can configure [[Nginx|CloudBeaver-and-Nginx]], Apache or any other web server in front of it.

*Note: you must be in the server root directory to run it.*  
If you need to run it from some other directory, then you can set the environment variable `CLOUDBEAVER_HOME` to the server root directory.