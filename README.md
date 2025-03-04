# 自动化订阅小姐姐影片

## 项目简介

本项目是一个自动化订阅小姐姐影片的应用，主要功能包括：
- **订阅影片**
- **订阅演员**
- **订阅榜单**
- **搜索查询**
- **支持企业微信交互**
- **支持企业微信，TG推送**
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
    image: /envyafish/byte-muse:latest
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
#### 自行激活 https://hub.docker.com/r/envyafish/byte-muse-license
