# Ledisdb

A docker image for https://github.com/siddontang/ledisdb with Rocksdb

## Usage

Server:
```
docker run --name=ledisdb -i -t --rm -p 6380:6380 -v ledisdb.conf:/ledisdb.conf -v data:/data ledisdb
```

Modo Daemon
```
docker run --name=ledisdb -d --restart=on-failure:3 -p 6380:6380 -v ledisdb.conf:/ledisdb.conf -v data:/data ledisdb
```

Client:
```
docker run -it --rm --link ledisdb:ledisdb ledisdb ledis-cli -h ledisdb
