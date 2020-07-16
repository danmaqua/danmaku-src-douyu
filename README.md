Douyu 弹幕源服务
=======

以开放的协议为 Danmaqua 产品或第三方产品提供 Douyu 直播平台的实时弹幕连接服务

## 为什么做这个？

将直播平台同传弹幕转发至即时通讯软件的机器人需要支持多平台，在无需修改机器人代码的情况下接入不同平台的弹幕，需要将他们的数据转换为统一的规范格式，并且使用开放的协议与机器人建立通讯。

本项目对于 Douyu 直播平台而言，是一个支持连接多个房间同时获取实时弹幕的客户端。对于 Danmaqua 产品或第三方产品而言，则是一个服务端。

有关于数据格式和协议可以阅读：<https://danmaqua.github.io/bot/dmsrc_api.html>

> 这个服务端不会保存弹幕数据到本地

## 如何使用？

Git Clone 本项目到本地，参照 `config.sample.json` 进行编辑并保存为 `config.json`

```json
{
    "//": "弹幕源服务器绑定的 IP 地址",
    "hostname": "127.0.0.1",
    
    "//": "弹幕源服务器绑定的端口",
    "port": 8002,
    
    "//": "弹幕源服务器与客户端协定的 Authorization 头部，如果不想使用可以留 null",
    "basicAuth": "testPassword",
    
    "//": "定时批量重新连接直播房间的计划时间，如果不想使用可以留 null",
    "reconnectCron": "0 0 3 * * *",
    
    "//": "日志保存目录",
    "logsDir": "./logs"
}
```

在项目目录中执行 `npm install` 安装必要的依赖。

完成依赖的安装后，执行 `npm start` 即可启动服务端。

## 原协议实现

本项目的 Douyu 弹幕协议使用了 [flxxyz/douyudm](https://github.com/flxxyz/douyudm) 库，感谢 flxxyz 大佬开发出可靠好用的 Node.js 库。

## 交流群

Telegram：[加入群组](https://t.me/joinchat/BmgWUhR48cf7ykWTxsUGCA)

## Licenses

MIT
