# openKB Docker Image

[This](https://hub.docker.com/r/toras9000/openkb) is a docker image of the Markdown Knowledge base application [openKB](https://github.com/mrvautin/openKB).  

## Tags

- latest ([Dockerfile](https://github.com/toras9000/docker-openkb/blob/master/build/Dockerfile))

## Usage
If you run for trial.  
The container provides services on port 4444.  

```bash
$ docker run -d -p 8000:4444 toras9000/openkb
```

## Data location
Assume that the following locations in the container are persisted:

- `/openkb/config`  
Storage directory for configuration file 'appsettings.json'.  
If there is a configuration file in this directory, it is copied to the application directory.  
If not, copy the application configuration file here.  

- `/openkb/data`  
Storage directory for default nedb files.

An example of persisting with built-in nedb is:
```bash
$ docker run -d \
             -p 8000:4444 \
             -v /opt/openkb/config:/openkb/config \
             -v /opt/openkb/data:/openkb/data \
             toras9000/openkb
```
