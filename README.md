# 请勿宣传此项目！！

## 食用方法

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
  # 若需要开启图书馆榜单,可自行部署如下服务。并于byte-muse项目中配置bypass_url
  cloudflarebypass:
    image: ghcr.io/sarperavci/cloudflarebypassforscraping:latest
    container_name: cloudflarebypass
    restart: always
    network_mode: bridge
    ports:
      - 8089:8000
    environment:
      - HTTP_PROXY=http://192.168.50.198:7890
      - HTTPS_PROXY=http://192.168.50.198:7890
      - DOCKERMODE=true

networks:
  bridge:
    driver: bridge
```
#### 首次启动 账号密码可在后台日志查看
