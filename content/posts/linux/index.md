---
weight: 1
title: "TQC Linux系統管理詳解"
date: 2022-05-10T11:48:01+08:00
draft: false
author: Kr1s

resources:
- name: "featured-image-preview"
  src: "linux_preview.png"

description: TQC Linux系統管理詳解

tags: ["TQC", "Linux"]
categories: ["IECS"]

lightgallery: true
---


<!--more-->

~~不專業詳解，我也是菜雞，看看就好~~

{{< admonition type = tip title = "點一下" open = false >}}
點開的TQC都滿分通過
{{< /admonition >}}

--- 

### 如附圖所示，該Script存放在~/bin目錄之下，然後使用者在家目錄內執行Script。請問當Script結束後，使用者的工作目錄會在下列哪一項？

- (A) ~/
- (B) ~/bin
- (C) /tmp
- (D) /   

**答案：(A)**


---


### 關於make menuconfig組態設定的敘述，下列哪些正確？(複選)

- (A) *代表內建到核心，M代表為外掛模組
- (B) *代表為外掛模組，M代表內建到核心
- (C) 設備組態內建到核心，核心檔較為龐大
- (D) 設備組態外掛模組，核心檔案較小  

**答案：(A)、(C)、(D)**


---

### 下列哪一項指令最適合針對某一Partition做備份？

- (A) archive
- (B) cpio
- (C) dump
- (D) tar   

**答案：(C)**


---

### 下列哪一行指令可將系統最新的兩秒程序資訊存在檔案proc.txt中，並且依CPU負載量為排序依據？

- (A) ps aux | awk '$3' | sort –n ; sleep 2 > proc.txt
- (B) top -d2 -n1 > proc.txt
- (C) top –d2 –n1 -b > proc.txt
- (D) ps -aux -d2 -n1 > proc.txt		   

**答案：(C)**


---
### 請問程序的資料會在下列哪一項目錄下？

- (A) /usr
- (B) /var
- (C) /proc
- (D) /lib   

**答案：(C)**


---