
# Genvoy - Backup
<a id="markdown-genvoy---backup" name="genvoy---backup"></a>

An extension for the Genvoy Framework to backup received event json payloads.

## Naming
<a id="markdown-naming" name="naming"></a>

genvoy ['jenvoi] is a name combination of both 'Generali' and 'generic' as prefix and 'envoy' as suffix. The word structure describes this solution as a generic approach to transmitting webhook messages (as an envoy) for the Generali.

This word construct only serves the purpose of simplified representation and description of the function of the software. It is not related to similar sounding products from other sectors or product areas and related components.  The function of the software is alternatively described by the longer name "github-webhooks-framework".

The name was changed 07/2020 from "github-webhooks-framework" to "genvoy" because the various functions called by a Webhook call are to be managed as separate repositories.A short name for the framework repository makes it easier to name the function repositories.

The Genvoy Framework can be found here: https://github.com/generaliinformatik/genvoy (alternatively: http://bit.ly/genvoy-framework)

## Purpose
<a id="markdown-purpose" name="purpose"></a>

This extension for the Genvoy framework provides a Python script that can be used to backup received paylods in a local directory by event. The script can be used to keep track of all received events. With the help of this script, events can be secured and stored locally, independent of external providers and services. The backup can then be persisted using an established backup mechanism.

## Table of content
<a id="markdown-table-of-content" name="table-of-content"></a>
<!-- TOC -->

- [Naming](#naming)
- [Purpose](#purpose)
- [Table of content](#table-of-content)
- [Installation](#installation)
- [Docker](#docker)
- [License](#license)

<!-- /TOC -->

## Installation
<a id="markdown-installation" name="installation"></a>

The following steps are required for commissioning:

1. Clone the Genvoy Framework repository (https://github.com/generaliinformatik/genvoy, alternatively: http://bit.ly/genvoy-framework)
2. Clone the Genvoy Backup repository
3. Copy the script `hooks/backup` from the Genvoy clone repository into the `hooks` directory of the Genvoy Framework directory
4. Name the script file in `{event}-backup` (where `{event}` is the event to be monitored, assuming e.g. `all`)
5. Set the execute flag of the script `hooks/all-backup` (via chmod +x)
6. Adjust the settings in the configuration file `app/hooks/backup.json` to your requirements

## Docker
<a id="markdown-docker" name="docker"></a>

To deploy in a Docker container you may want to persist your backuped data. Please map the backup dir to a local dir outside the container:

    docker run --name webhooks \
      -v /path/to/my/backups:/app/backups.json \
      -p 5000:5000 webhooks:latest


## License
<a id="markdown-license" name="license"></a>

APLv2, see [LICENSE](LICENSE)
