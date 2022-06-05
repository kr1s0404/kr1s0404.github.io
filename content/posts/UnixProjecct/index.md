---
weight: 1
title: "UNIX應用與實務 期末專題"
date: 2022-06-05T14:22:01+08:00
draft: false
author: 余睿霖、王昱智、王子杰

resources:
- name: "featured-image-preview"
  src: "UnixProject_preview.png"

description: 用樹莓派搭建BT下載伺服器

tags: ["Unix", "Linux", "Demo", "BT"]
categories: ["IECS"]

lightgallery: true
---


<!--more-->

~~不專業DEMO，看看就好~~

{{< admonition type = tip title = "組員" open = false >}}
余睿霖、王昱智、王子杰
{{< /admonition >}}

--- 

### 安裝指令

{{< image src = "install.jpg" caption = "安裝指令" >}}

```shell
sudo apt-get install transmission-daemon
```

---

### 建立資料夾指令

接著建立下載目錄，一個是下載完成的目錄
一個是未完成的目錄，具體目錄根據你的情況決定：

{{< image src = "mkdir.jpg" caption = "建立資料夾指令" >}}

```shell
mkdir -p /home/pi/incomplete # for incomplete downloads
mkdir /home/pi/complete # finished downloads
```

---


### 修改目錄權限

接著建立下載目錄，一個是下載完成的目錄
一個是未完成的目錄，具體目錄根據你的情況決定：

{{< image src = "mkdir.jpg" caption = "修改目錄權限" >}}

```bash
sudo usermod -a -G debian-transmission pi
chgrp debian-transmission /home/pi/incomplete
chgrp debian-transmission /home/pi/complete
chmod 770 /home/pi/incomplete
chmod 770 /home/pi/complete
```

---


### 修改配置文件

修改配置文件 /etc/transmission-daemon/settings.json
這是一個 json 格式的文件，配置項很多，但主要改下面這些：
下載目錄位置：

{{< image src = "json.jpg" caption = "修改配置文件" >}}

```json
"download-dir": "/home/pi/complete",
未完成的下载目录
"incomplete-dir": "/home/pi/incomplete",
允许Web访问的白名单地址
"rpc-whitelist": "你樹莓派的IP位置（例如192.168.1.*）",
```

---