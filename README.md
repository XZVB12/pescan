![exe logo](https://github.com/malice-plugins/exe/blob/master/docs/exe.png)

# malice-exe

[![Circle CI](https://circleci.com/gh/malice-plugins/exe.png?style=shield)](https://circleci.com/gh/malice-plugins/exe) [![License](http://img.shields.io/:license-mit-blue.svg)](http://doge.mit-license.org) [![Docker Stars](https://img.shields.io/docker/stars/malice/exe.svg)](https://hub.docker.com/r/malice/exe/) [![Docker Pulls](https://img.shields.io/docker/pulls/malice/exe.svg)](https://hub.docker.com/r/malice/exe/) [![Docker Image](https://img.shields.io/badge/docker%20image-81.5MB-blue.svg)](https://hub.docker.com/r/malice/exe/)

Malice PExecutable Plugin

> This repository contains a **Dockerfile** of **malice/exe**.

---

## Dependencies

- [malice/alpine](https://hub.docker.com/r/malice/alpine/)

## Installation

1. Install [Docker](https://www.docker.io/).
2. Download [trusted build](https://hub.docker.com/r/malice/exe/) from public [DockerHub](https://hub.docker.com): `docker pull malice/exe`

## Usage

```bash
$ docker run --rm -v /path/to/malware:/malware malice/exe --help

Usage: pescan [OPTIONS] COMMAND [ARGS]...

  Malice PExecutable Plugin

  Author: blacktop <https://github.com/blacktop>

Options:
  --version   print the version
  -h, --help  Show this message and exit.

Commands:
  scan  scan a file
  web   start web service
```

### Scanning

```bash
$ docker run --rm -v /path/to/malware:/malware malice/exe scan --help

Usage: pescan.py scan [OPTIONS] FILE_PATH

  Malice EXE Plugin.

Options:
  -v, --verbose            verbose output
  -t, --table              output as Markdown table
  -x, --proxy PROXY        proxy settings for Malice webhook endpoint [$MALICE_PROXY]
  -c, --callback ENDPOINT  POST results back to Malice webhook [$MALICE_ENDPOINT]
  --elasticsearch HOST     elasticsearch address for Malice to store results [$MALICE_ELASTICSEARCH]
  --timeout SECS           malice plugin timeout (default: 10) [$MALICE_TIMEOUT]
  --extract PATH           where to extract the embedded objects to
                           (default: /malware) [$MALICE_EXTRACT_PATH]
  --peid PATH              path to the PEiD database file (default: peid/UserDB.TXT) [$MALICE_PEID_PATH]
  -h, --help               Show this message and exit.
```

This will output to stdout and POST to malice results API webhook endpoint.

## Sample Output

### [JSON](https://github.com/malice-plugins/exe/blob/master/docs/results.json)

```json
{
  "exe": {}
}
```

### [Markdown](https://github.com/malice-plugins/exe/blob/master/docs/SAMPLE.md)

---

#### exe

---

## Documentation

- [To write results to ElasticSearch](https://github.com/malice-plugins/exe/blob/master/docs/elasticsearch.md)
- [To create a pe scan micro-service](https://github.com/malice-plugins/exe/blob/master/docs/web.md)
- [To post results to a webhook](https://github.com/malice-plugins/exe/blob/master/docs/callback.md)

## Issues

Find a bug? Want more features? Find something missing in the documentation? Let me know! Please don't hesitate to [file an issue](https://github.com/malice-plugins/exe/issues/new)

## CHANGELOG

See [`CHANGELOG.md`](https://github.com/malice-plugins/exe/blob/master/CHANGELOG.md)

## Contributing

[See all contributors on GitHub](https://github.com/malice-plugins/exe/graphs/contributors).

Please update the [CHANGELOG.md](https://github.com/malice-plugins/exe/blob/master/CHANGELOG)

## Credits

Heavily (if not entirely) influenced by the [viper PE module](https://github.com/viper-framework/viper/blob/master/viper/modules/pe.py) and by CSE's [alsvc_pefile](https://bitbucket.org/cse-assemblyline/alsvc_pefile)

## TODO

- [ ] activate dumping functionality
- [ ] add timeout protection
- [ ] revisit security/signature stuff
- [ ] add proxy settings for callback POST

## License

MIT Copyright (c) 2016 **blacktop**
