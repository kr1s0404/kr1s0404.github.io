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

## 安裝指令

{{< image src = "install.jpg" caption = "安裝指令" >}}

```shell
sudo apt-get install transmission-daemon
```

---

## 建立資料夾指令

接著建立下載目錄，一個是下載完成的目錄  
一個是未完成的目錄，具體目錄根據你的情況決定：  

{{< image src = "mkdir.jpg" caption = "建立資料夾指令" >}}

```shell
mkdir -p /home/pi/incomplete # 未完成的目錄
mkdir /home/pi/complete # 下載完成的目錄
```

---


## 修改目錄權限

接著建立下載目錄，一個是下載完成的目錄
一個是未完成的目錄，具體目錄根據你的情況決定：

{{< image src = "mod.jpg" caption = "修改目錄權限" >}}

```shell
sudo usermod -a -G debian-transmission pi
sudo chgrp debian-transmission /home/pi/incomplete
sudo chgrp debian-transmission /home/pi/complete
sudo chmod 770 /home/pi/incomplete
sudo chmod 770 /home/pi/complete
##記得加sudo
```

---


## 修改配置文件

### 如果不知道如何修改JSON文件的話，可以用以下指令
{{< image src = "nano.jpg" caption = "修改JSON文件" >}}

```shell
sudo nano /etc/transmission-daemon/settings.json
```

> nano是個好用的工具，跟vim很像  

---

修改配置文件 /etc/transmission-daemon/settings.json  
這是一個 json 格式的文件，配置項很多，但主要改下面這些：  

{{< image src = "json.jpg" caption = "修改配置文件" >}}
{{< image src = "json2.jpg" caption = "修改配置文件" >}}

```json
"download-dir": "/home/pi/complete",
未完成的下載目錄
"incomplete-dir": "/home/pi/incomplete",
允許Web訪問的白名單地址
"rpc-whitelist": "你樹莓派的IP位置（例如192.168.1.*）",
```

### 如果不知道自己的樹莓派IP，可以用以下指令查看
{{< image src = "checkip.jpg" caption = "查看IP" >}}

```shell
ifcongfig -a
```

---


## 重啟 transmission

最後，配置好之後重啟 transmission
注意以下兩個命令按順序執行，單獨 restart 的話配置不會保存：

{{< image src = "restart.jpg" caption = "重啟 transmission" >}}

```shell
sudo service transmission-daemon reload
sudo service transmission-daemon restart
```

---


## 連上伺服器

在瀏覽器中輸入 IP 加 PORT: 9091  
比如： http://192.168.1.3:9091/   
進入時輸入帳號和密碼，默認都是：transmission 。  
你現在已經有了一個獨立的 BT 下載伺服器了！  
界面功能完善，可以做限速等設置。

{{< image src = "login.jpg" caption = "連上伺服器" >}}


---


## 下載畫面

外出或睡覺的時候就不用開著電腦下載了，而且更省電。

{{< image src = "download.png" caption = "下載畫面" >}}


---

## 實驗心得

> 樹莓派的存儲設備為 SD 卡，存儲容量不大，不適合做 BT 的存儲器，最好還是外接移動硬碟。  
這裡要注意的是由於樹莓派供電的問題。樹莓派 3B 供電不能直接外接移動硬碟，需要一個可接電源的 USB HUB 對移動硬碟單獨供電。  
樹莓派 4B 可以直接外接固態硬盤。
可以先在要掛載的目錄下新建一個資料夾，然後將移動硬碟掛載即可。  
為了能夠在樹莓派重啟的時候自動完成掛載操作，可以將掛載設置為系統服務。

{{< image src = "disk.jpg" caption = "下載畫面" >}}