# GitHub Action to Docker Build

![https://github.com/zmicro-design/action-docker-build](https://img.shields.io/github/v/release/zmicro-design/action-docker-build)
![https://github.com/zmicro-design/action-docker-build](https://github.com/zmicro-design/action-docker-build/workflows//Publish/badge.svg)

### Usage

| option | required | description |
| ------ | -------- | ----------- |
| tags | false | specify build tags |
| push   | false | specify whether to push remote |
| build-args | false | specify build build-args |
| platforms | false | specify build platforms |
| cache-from | false | specify build cache-from |
| cache-to | false | specify build cache-to |
| labels | false | specify build labels |

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
        uses: zmicro-design/action-docker-build@v1
        with:
          build-args: |
            VERSION=${{ steps.meta.outputs.version }}
          context: .
          push: ${{ github.event_name != 'pull_request' }}
          cache-from: type=registry,ref=${{ steps.meta.outputs.name }}:buildcache
          cache-to: type=registry,ref=${{ steps.meta.outputs.name }}:buildcache,mode=max
          tags: ${{ steps.meta.outputs.tags }}
          labels: ${{ steps.meta.outputs.labels }}
          platforms: linux/amd64
```

### License

[MIT](./LICENSE)
