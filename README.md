# alpine-pkg-kafkacat

[![CircleCI](https://circleci.com/gh/sgerrand/alpine-pkg-kafkacat.svg?style=svg)](https://circleci.com/gh/sgerrand/alpine-pkg-kafkacat)

This is [Kafkacat][kafkacat] as an Alpine Linux package.

## Releases

See the [releases page](https://github.com/sgerrand/alpine-pkg-kafkacat/releases) for the latest
download links.

## Installing

The current installation method for these packages is to pull them in using
`wget` or `curl` and install the local file with `apk`:

    apk --no-cache add ca-certificates wget
    wget --quiet --output-document=/etc/apk/keys/sgerrand.rsa.pub https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub
    wget https://github.com/sgerrand/alpine-pkg-kafkacat/releases/download/1.6.0-r0/kafkacat-1.6.0-r0.apk
    apk add --no-cache kafkacat-1.6.0-r0.apk

[kafkacat]: https://github.com/edenhill/kafkacat
