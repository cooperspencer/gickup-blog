---
Title: Methods to install
weight: 2
---

### Binary

Download the [latest release](https://github.com/cooperspencer/gickup/releases/latest) for your OS and architecture from Github and unpack it.
Alternatively, you can copy the `gickup` binary to a directory from your `$PATH` variable, to use it globally.

#### Linux/Mac

```bash
./gickup conf.yml
```

#### Windows

```cmd
gickup.exe conf.yml
```

### Docker

You can grab the latest version of gickup from [Github](https://github.com/cooperspencer/gickup/pkgs/container/gickup) or [Docker](https://hub.docker.com/r/buddyspencer/gickup).

#### Pure Docker

```bash
docker pull buddyspencer/gickup
docker run -d -v /path/to/conf.yml:/gickup/conf.yml buddyspencer/gickup
```

#### Docker Compose

If you prefer to use docker compose, grab the [docker-compose.yml](https://github.com/cooperspencer/gickup/blob/main/docker-compose.yml) from the repository.

```bash
docker compose up -d
```

### Compile it yourself

If you want to use the latest version of the `main` branch, you can also compile it yourself.

Prerequisits:
- [git](https://git-scm.com/)
- [go](https://go.dev/)

```bash
git clone https://github.com/cooperspencer/gickup
cd gickup
go build .
```
