# mumbledj

## Description

A small container for running the glorious [mumbledj](https://github.com/matthieugrieger/mumbledj) application for your [mumble](https://www.mumble.info) server built from an Alpine base.

## Usage

The recommended way to run this container is as follows:

```bash
$ docker run -d mattikus/murmur --server <Mumble Server IP> --port <Mumble Server Port>
```

## Important notes

### Getting API Keys

This application requires either a YouTube or SoundCloud API key to function well. See the [mumbledj documentation](https://github.com/matthieugrieger/mumbledj#youtube-api-key) for instructions on how to acquire these keys.

### Providing your own configuration

If you want to tweak the default `config.yaml`, you should run:

```bash
docker cp your-container-name:/root/.config/mumbledj/config.yaml ./config.yaml
```

To run the container with your tweaked configuration file:

```bash
$ docker run -d -v /path/to/mumbledj/config.yaml:/root/.config/mumbledj/config.yaml mattikus/mumbledj <ARGS>
```

