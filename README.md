# alpine-pkg-kafkacat

[![CircleCI](https://circleci.com/gh/sgerrand/alpine-pkg-kafkacat.svg?style=svg)](https://circleci.com/gh/sgerrand/alpine-pkg-kafkacat)

This is [Kafkacat][kafkacat] as an Alpine Linux package.

## Releases

See the [releases page](https://github.com/sgerrand/alpine-pkg-kafkacat/releases) for the latest
download links.

## Installing

The current installation method for this packages is to install it with `apk`:

    wget --quiet --output-document=/etc/apk/keys/sgerrand.rsa.pub https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub
    apk --no-cache --no-progress --repository https://apkproxy.herokuapp.com/sgerrand/alpine-pkg-kafkacat add kafkacat=1.3.1-r0

[kafkacat]: https://github.com/edenhill/kafkacat
