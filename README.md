## Description

A small container for running the glorious [mumbledj](https://github.com/matthieugrieger/mumbledj) application for your [mumble](https://www.mumble.info) server built from an Alpine base.

It's configured to use `/etc/mumbledj.yaml` as the default configuration path.

## Usage

The recommended way to run this container is as follows:

```bash
$ docker run -d mattikus/murmur --server <mumble server ip> --port <mumble server port>
```

## Important notes

### Getting API Keys

This application requires either a YouTube or SoundCloud API key to function well. See the [mumbledj documentation](https://github.com/matthieugrieger/mumbledj#youtube-api-key) for instructions on how to acquire these keys.

### Providing your own configuration

If you want to tweak the default `config.yaml`, you should run this after running your container at least once:

```bash
docker cp your-container-name:/root/.config/mumbledj/config.yaml ./mumbledj.yaml
```

To run the container with your tweaked configuration file:

```bash
$ docker run -d -v /path/to/your/mumbledj.yaml:/etc/mumbledj.yaml mattikus/mumbledj <args>
```

