# GitHub Action to Docker Build

![https://github.com/zmicro-design/action-setup-docker-build](https://img.shields.io/github/v/release/zmicro-design/action-setup-docker-build)
![https://github.com/zmicro-design/action-setup-docker-build](https://github.com/zmicro-design/action-setup-docker-build/workflows//Publish/badge.svg)

### Usage

| option | required | description |
| ------ | -------- | ----------- |

### Example

```yml
name: CI

on: [push]

jobs:
  build:
    name: Test
    runs-on: ubuntu-latest
    steps:
      - name: Docker Build
        uses: zmicro-design/action-setup-docker-build@v1
```

### License

[MIT](./LICENSE)
