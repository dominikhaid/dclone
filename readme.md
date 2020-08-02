---
title: DCLONE
author: Dominik Haid
date: 02.08.2019
---

<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

<!-- code_chunk_output -->

- [DCLONE](#dclone)
  - [description](#description)
  - [usage](#usage)
    - [init](#init)
    - [use](#use)
- [TODO](#todo)

<!-- /code_chunk_output -->

# DCLONE

## description

```
DCLONE is a simple shell script. It is used to backup and sync docker container,
images and volumes to easly or sync everything from to another place.
DCLONE is build for working with docker-compose files.
How ether it will work with every docker container.
```

## usage

#### init

1. copy the backup.sh file in the directory of your docker-compose.yml
2. open the backup.sh in any text editor
3. set the IMAGES variable like IMAGES=(imagename1 imagename2)
4. set the CONTAINER variable like CONTAINER=(MyContainer1 MyContainer2)
5. set VOLUME variables like VOLUME=(MyContainer1!volumeName:/path/in/docker
   MyContainer2!./mount/path:/path/in/docker)

**note**

```
volumes schema is ContainerName then ! to split the string then VolumeName:/path/in/docker
or ContainerName then ! to split the string then ./local/path:/path/in/docker

example named volume:
VOLUME=(mysqlDB!data:/var/lib/mysql)
or:
VOLUME=(mysqlDB!./data:/var/lib/mysql)

```

### run

1. run bash backup.sh -f -i -v to backup everything
2. copy the backup.sh to you local folder run docker -d to download tge backup
   folder created in last step
3. run bash backupösh -r to restore the saved files to you local docker
   instance

you can ow sync and copy the docker container with all volumes or/and images
between the two destinations

**note**

```
you can now run "bash backup.sh" with the following parmaters.

bash backup.sh -f    backup files like docker-compose.yml / DOCKERFILE / .dockerignore
bash backup.sh -i    backup the defined images
bash backup.sh -v    backup the defined volumes
bash backup.sh -d    to download the backup folder from the defined server to your folder
bash backup.sh -u    to upload the backup folder from you location to the server
bash backup.sh -r    to restore and import all files in your backup folder to docker

you can combine all params like bash backup.sh -f -i -v or any other combination
```

```
set the SERVER variable to the absolute path of your docker directory if you want to use the upload and download funktion to sync files.
PATH musst be set like SERVER='user@XXX.XXX.XXX.XXX:/abspath/to/your/folder'
```

# TODO

1. simplefy the setup process or automate

**notes**

```
i just quickly wrote this to move docker containers that i use frequently.
feel free to use add or change it
```
