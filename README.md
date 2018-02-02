# How to install Army ANT using Docker Compose
```bash
$ git clone git@github.com:feup-infolab/army-ant-install.git
$ cd army-ant-install
$ docker-compose up
```

This will create two containers, one for MongoDB, including preloaded document metadata, and another one for Army ANT server that depends on the MongoDB instance.