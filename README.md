# 请勿宣传此项目！！

## 食用方法
```
docker run
  -d
  --name='byte-muse'
  --net='bridge'
  -p 8043:80
  -v /mnt/user/appdata/byte-muse:/data 
  /envyafish/byte-muse:latest
```

```
version: '3'
services:
  byte-muse:
    image: envyafish/byte-muse:latest
    container_name: byte-muse
    restart: always
    networks:
      - bridge
    ports:
      - "8043:80"
    volumes:
      - /mnt/user/appdata/byte-muse:/data

networks:
  bridge:
    driver: bridge
```
#### 首次启动 账号密码可在后台日志查看
