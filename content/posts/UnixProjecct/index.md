---
weight: 1
title: "TQC Linux系統管理詳解"
date: 2022-05-10T11:48:01+08:00
draft: false
author: Kr1s

resources:
- name: "featured-image-preview"
  src: "UnixProject_preview.png"

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

> 我找不到這道題目的圖片...


---


### 關於make menuconfig組態設定的敘述，下列哪些正確？(複選)

- (A) *代表內建到核心，M代表為外掛模組
- (B) *代表為外掛模組，M代表內建到核心
- (C) 設備組態內建到核心，核心檔較為龐大
- (D) 設備組態外掛模組，核心檔案較小  

**答案：(A)、(C)、(D)**

> 找不到詳解 0.0

---

### 下列哪一項指令最適合針對某一Partition做備份？

- (A) archive
- (B) cpio
- (C) dump
- (D) tar   

**答案：(C)**

- (A) archive
  > 好像沒有這個指令
- (B) cpio
  > cpio命令是一個歸檔程序，它將一列文件複製到一個單一的、大的輸出文件。這個命令在各個文件之間插入了標題，以方便恢復。
- (C) dump
  > dump命令是Unix和類Unix操作系統上的一個程序，用於備份文件系統。它對塊進行操作，低於文件系統的抽象概念，如文件和目錄。 Dump可以將文件系統備份到磁帶或其他磁盤。它經常在網絡上使用，通過bzip2和SSH將其輸出管道化。
- (D) tar
  > Linux中的 "tar "代表磁帶歸檔，用於創建歸檔文件和提取歸檔文件。 Linux中的tar命令是Linux中提供歸檔功能的重要命令之一。我們可以使用Linux的tar命令來創建壓縮或未壓縮的歸檔文件，也可以維護和修改它們。  

  `` tar [options] [archive-file] [file or directory to be archived] ``


---

### 下列哪一行指令可將系統最新的兩秒程序資訊存在檔案proc.txt中，並且依CPU負載量為排序依據？

- (A) ps aux | awk '$3' | sort –n ; sleep 2 > proc.txt
- (B) top -d2 -n1 > proc.txt
- (C) top –d2 –n1 -b > proc.txt
- (D) ps -aux -d2 -n1 > proc.txt		   

**答案：(C)**

> top是效能分析工具，能夠即時顯示系統中各個行程的資源佔用狀況。

|   參數  |         說明        |
| -------| --------------------|
| b      | Batch mode          |
| d      | 指定更新時間（單位:秒） |
| o      | 指定要輸出的欄位名稱   |
| p      | 指定要觀察的pid       |
| u      | 指定要觀察的使用者名稱  |

> 除了開啟top觀察系統資訊外top也可以使用指令將資訊直接回傳至營幕，若再使用">"或">>"則可將結果匯出為檔案

---
### 請問程序的資料會在下列哪一項目錄下？

- (A) /usr
- (B) /var
- (C) /proc
- (D) /lib   

**答案：(C)**

>在許多類 Unix 電腦系統中， procfs 是 行程 檔案系統 的縮寫，包含一個偽檔案系統，用於通過核心存取行程資訊。這個檔案系統通常被掛載到 /proc 目錄。由於 /proc 不是一個真正的檔案系統，它也就不占用儲存空間，只是占用有限的記憶體。

---