
By default CloudBeaver keeps all data on disk in a volume `/opt/cloudbeaver`. By default this volume mounted to host machine folder `/var/cloudbeaver` or `/var/cloudbeaver-ee`.

It makes sense to backup this directly from time time and also before product version upgrade.  
To archive entire workspace run
```sh
tar czvf backup.tgz /var/cloudbeaver/
```
or
```sh
tar czvf backup.tgz /var/cloudbeaver-ee/
```

then move `backup.tgz` to a safe place.

Note: if your server has high load it makes sense to stop it before making a backup. Just run `docker stop cloudbeaver-ee` before backup and `docker start cloudbeaver-ee` after.  