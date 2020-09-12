<br />
<br />

# 1. DCLONE - Docker Container Backup Script


<br />
<br />

## 1.1. Description

```
Shell script used to backup and restore Docker container with all images and volumes.
Remote up and download backup via sftp. Designed for docker-compose.yml files.
```

<br />
<br />

## 1.2. Setup

1. place backup.sh in the same folder as your docker-compose.yml
2. open the backup.sh in any text editor
3. set the variables

``` 

IMAGES=(nginx php) -> images to backup as shell array
CONTAINER=(nginx php-fpm) -> containers to backup as shell array
VOLUME=(nginx!./nginx:/etc/nginx!./html:/usr/share/nginx/html php-fpm!./html:/usr/share/nginx/html)  -> combination container!volumePath as array
SERVER='user@0.0.0.0:/abspath/to/docker-compose/folder' -> remote host for upload/download function
BACKUPFOLDER=docker-backups
```


### 1.3 Options

1. bash backup.sh -f -i -v -> backup docker files, images, volumes
3. bash backup.sh -f  -> backup docker files
4. bash backup.sh -i  -> backup docker images
4. bash backup.sh -v  -> backup docker volumes
5. bash backup.sh -r  -> backup restore all files from the backup-foilder
6. bash backup.sh -u -> upload all files from back-folder to remote host
6. bash backup.sh -d -> download all files from the remote host to the backup-folder

