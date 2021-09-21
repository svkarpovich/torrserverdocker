# torrserver
### Unofficial Docker Image for TorrServer

This is unofficial dockerized precompiled TorrServer within a debian:stable-slim image.

"TorrServer, stream torrent to http"

![TorrServer](https://raw.githubusercontent.com/MrKsey/torrserver/master/ts.jpg)

More info:
- https://github.com/YouROK/TorrServer
- https://4pda.ru/forum/index.php?showtopic=889960

### Requirements

* server with docker
* ~256 Mb RAM, ~512 Mb disk space 

### Installing

- сreate "/torrserver/db" directory (for example) on your host
- (optional) put ["ts.ini"](https://raw.githubusercontent.com/MrKsey/torrserver/master/ts.ini) file to "/torrserver/db", uncomment the desired options. The "cron_task" parameter (in the cron format) is used to start updates on a schedule. Parameters from "ts.ini" file overwrites the default parameters.
- connect host directory "/torrserver/db" to the container directory "/TS/db" and start container:
```
docker run --name torrserver -e TZ=Europe/Moscow -d --restart=always --net=host -v /torrserver/db:/TS/db ksey/torrserver
```



















### YouROK/TorrServer last 5 commits:
* 2021-09-13 19:28:50: [YouROK/TorrServer, COMMIT] move meta objects to getTorrentMeta
* 2021-09-13 16:39:55: [YouROK/TorrServer, COMMIT] skip loopback and tunnels for dlna
* 2021-09-13 16:28:05: [YouROK/TorrServer, COMMIT] Update list.go
* 2021-09-13 16:25:45: [YouROK/TorrServer, COMMIT] Revert "return NoSuchObject in case no meta"
* 2021-09-13 16:25:40: [YouROK/TorrServer, COMMIT] Revert "change meta response"
