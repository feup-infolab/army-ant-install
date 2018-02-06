# How to install Army ANT using Docker Compose

```bash
$ git clone git@github.com:feup-infolab/army-ant-install.git
$ cd army-ant-install
$ docker-compose up
```

This will create two containers, one for MongoDB, including preloaded document metadata, and another one for Army ANT server that depends on the MongoDB instance.

## Multiple instances

You might want to run different instances of Army ANT, for different projects. Let's say that you are, for example, working on two papers and would like to do several runs per paper without mixing them in the same instance.

You can do this by launching separate Army ANT instances, using:

```bash
$ docker-compose -p ijr2018 up
```

This will launch a separate instance that, unless you call `docker-compose -p ijr2018 down`, you will be able to restore just like the default instance.

Each Army ANT instance creates a volume that maps the local directory `collections` to `/opt/army-ant/collections/external`, enabling indexing operations to run inside the container. Please view [Army ANT Examples](https://github.com/feup-infolab/army-ant/blob/0.3/EXAMPLES.md) to learn the syntax. Any command within the container can be launched using:

```bash
$ docker exec -i -t irj2018_army-ant_1 ./army-ant.py ...
```

Where `ijr2018` is the name of the project assigned with `docker-compose`.

### Ideas on archival

We are also considering a way to backup your session for archival, but this is something that might be hard to do, as we do not want backward compatibility to be a requirement in Army ANT, in order to avoid it becoming a stagnant project. Freedom to change code is essential in a set for innovation.

## Evaluation Data

Each milestone release of [Army ANT](https://github.com/feup-infolab/army-ant/releases) should include a set of asset files with evaluation data for the preloaded indexes. For example, [release 0.3](https://github.com/feup-infolab/army-ant/releases/tag/0.3) of Army ANT includes `inex_3t_nl-documents.json.gz`, corresponding to the JSON preloaded in the MongoDB instance, as well as `inex-2009-3t-nl.zip`, an archive with the indexed collection, which includes topics and relevance judgments to test the evaluation features provided by Army ANT via its web interface. Further information about the asset files attached to each release can be found in the [DOCKER.md](https://github.com/feup-infolab/army-ant/blob/0.3/DOCKER.md) of the corresponding release.