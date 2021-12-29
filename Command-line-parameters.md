CloudBeaver support the same [[system parameters|https://github.com/dbeaver/dbeaver/wiki/Command-Line#system-parameters]] as DBeaver.

There are two ways to pass command line parameters to CloudBeaver server

### Modify run-server script

- Modify `run-server.sh` script, add extra parameters after `java` command in last line.
For example, add parameter `-Xmx2048` in server start: 
```sh
java -Xmx2048M -jar ${launcherJar} -product io.cloudbeaver.product.ce.product -web-config conf/cloudbeaver.conf -nl en -registryMultiLanguage
```

### Pass parameters using the environment variable

Set variable `JAVA_OPTS` to appropriate parameters value. 
For example, add parameter `-Xmx2048` in server start: 
```sh
export JAVA_OPTS=-Xmx2048
./run-server.sh
```
You can pass JAVA_OPTS variable to docker container by using `-e` docker parameter:
```sh
sudo docker run -d --restart unless-stopped -p 80:8978 \
  -e JAVA_OPTS=-Xmx2048 \ 
  -v /var/cloudbeaver/workspace:/opt/cloudbeaver/workspace dbeaver/cloudbeaver:latest`}
```
