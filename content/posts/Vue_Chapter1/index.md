---
weight: 1
title: "Chapter 1 | Vue.js基礎入門"
date: 2022-10-12T11:48:01+08:00
draft: false
author: Kr1s

resources:
- name: "featured-image-preview"
  src: "vue_preview.png"

description: Vue (音同View) 是一套以視圖層為基礎發展的 JavaScript 漸進式框架。與其他前端框架/函式庫不同的是，Vue.js 的目標是透過簡單的 API 提供開發者實作資料綁定與操作網頁上的元件，同時也因為 Vue.js 的核心把焦點關注在狀態與畫面的同步層級上，遂能夠輕易地與其他 JavaScript 函式庫、前端開發工具鍊等整合使用，成為一套完整的前端開發方案。

tags: ["軟體工程", "Vue", "Web", "JavaScript"]
categories: ["IECS"]

lightgallery: true
---

<!--more-->

## D0977669 資訊三乙 余睿霖

---

## Chapter 1 | Vue.js基礎入門

---


## 什麼是 漸進式 JavaScript 框架 (The Progressive JavaScript Framework)?

> 漸進式JavaScript指的是可以由淺入深，由簡單到困難的一種方式，“vue.js”就是一種漸進式JavaScript框架；漸進式也就是階梯式向前，例如vue的漸進式表現在聲明式渲染、組件系統、客戶端路由、大數據裝填管理、構建工具。   
  [前往查看文章](https://www.php.cn/website-design-ask-494424.html)


---


## 什麼是 MVVM 模式?


> - **MVVM代表的是：Model - View - ViewModel**   
> - **為什麼要使用MVVM：我們要將UI畫面跟Function邏輯分開**  
> - **Model：Model代表的是一個我們定義的一個物件所擁有的屬性，例如我們定義一個'使用者'的Model，那他可以擁有姓、名、帳號、密碼、電子郵件、生日...等等的屬性**
> - **View：View是產生畫面給使用者看的，他會根據Model的屬性數值而產生相對應的UI**  
> - **ViewModel：ViewModel是處理程式邏輯的地方，他會將View跟Model做連結，當使用者在View上做出操作時，會透過ViewModel處理背後的程式邏輯，接著更動Model的數值。在iOS App開發的MVVM系統模式下，ViewModel會通知View：「Model的值更動了，請重新渲染View」。**  

---


## 什麼是元件(component)系統?

> 將應用的元件化之後，代表同樣邏輯、同樣模板的東西可以重複拿來使用。Vue.js 的元件系統則是將此一概念再加以簡化，最小單位不一定如網頁般只能是 Node 的節點，它也可以是組合好的元件單元，就像我們平常玩的樂高積木一樣。元件 (Component) 的最小單位可以只是節點，也可以是好幾個節點組合而成的元件，甚至元件內還可有元件。
每個元件都有屬於自己的模板、程式邏輯，以及樣式，而整個網頁由這些元件構成起來，便成了元件樹 (Component tree)。

{{< image src = "1-1-component-tree.png" caption = "元件樹" >}}


---


## vue2, vue3 有哪些的差異?


---


## 用 vue3 寫一個 hello world 需要那些程式碼?


---



## computed/methods 差別在哪?html 中 v- 開頭的屬性有什麼用途? 請舉例?


---


## html 中 v- 開頭的屬性有什麼用途? 請舉例?


---


## 怎麼實作一個按鈕(button)事件?


---



## 請舉例一個 v-for 的用途?


---



## 請用自己的話解釋 vue 元件的 生命週期 (life cycle) 與更新機制?


---
