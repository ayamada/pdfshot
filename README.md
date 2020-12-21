# pdfshot

[![build](https://github.com/xcoo/pdfshot/workflows/build/badge.svg)](https://github.com/xcoo/pdfshot/actions?query=workflow%3Abuild)
[![DockerHub](https://img.shields.io/docker/v/xcoo/pdfshot)](https://hub.docker.com/r/xcoo/pdfshot)

PDF screenshot generator for web pages

## Run pdfshot

```shell
$ docker pull xcoo/pdfshot:0.1.1
$ docker run --rm --cap-add=SYS_ADMIN -e "PDFSHOT_PORT=8000" -p 8000:8000 xcoo/pdfshot:0.1.1
```

## Usage

```shell
$ curl -fsLJO 'localhost:8000/print.pdf?target=https%3A%2F%2Fwww.google.com&wait_for=%23body'
```

- `target` (Required)
  - The URL for which you want to get the screenshot.
  - `https://www.google.com`
- `wait_for` (Optional)
  - Wait for the screenshot until the selector you specified appears on the page.
  - `#body`

## Build Requirements

- Leiningen

## Build Docker image

```shell
$ lein cljsbuild once
$ docker build -t xcoo/pdfshot:latest .
$ docker-compose up -d
```

## Local execution

```shell
$ lein cljsbuild once
$ node target/pdfshot.js
```

## License

Copyright [Xcoo, Inc.][xcoo]

Licensed under the [Apache License, Version 2.0][apache-license-2.0].

[xcoo]: https://xcoo.jp
[apache-license-2.0]: http://www.apache.org/licenses/LICENSE-2.0.html
