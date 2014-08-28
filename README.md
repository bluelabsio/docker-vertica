# Docker Image for Vertica

Warning: This is very experimental. The level of testing has consisted of "Start server, run some sql, shutdown server, restart server, run some sql". What it does manage to do is get a vertica process up and running in a docker container. For the purposes of testing applications with fig and such, this might be sufficient, but don't let it anywhere near production.

The image creates a database called docker, with a blank dbadmin password.

## Usage:

Download the Vertica RPM from https://my.vertica.com and put it in this folder.
Then run:
```bash
docker build -t bluelabs/vertica .
```

### To run without a persistent datastore
```bash
docker run -P  bluelabs/vertica
```

### To run with a persistent datastore
```bash
docker run -P -v /path/to/vertica_data:/home/dbadmin/docker bluelabs/vertica
```
