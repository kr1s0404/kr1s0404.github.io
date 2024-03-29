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
> - **ViewModel：ViewModel是處理程式邏輯的地方，他會將View跟Model做連結，當使用者在View上做出操作時，會透過ViewModel處理背後的程式邏輯，接著更動Model的數值。在iOS App開發的MVVM系統模式下，ViewModel會通知View：「Model的值更動了，請重新渲染View」，所以我猜Vue應該也會吧（？。**  

---


## 什麼是元件(component)系統?

> 將應用的元件化之後，代表同樣邏輯、同樣模板的東西可以重複拿來使用。Vue.js 的元件系統則是將此一概念再加以簡化，最小單位不一定如網頁般只能是 Node 的節點，它也可以是組合好的元件單元，就像我們平常玩的樂高積木一樣。元件 (Component) 的最小單位可以只是節點，也可以是好幾個節點組合而成的元件，甚至元件內還可有元件。
每個元件都有屬於自己的模板、程式邏輯，以及樣式，而整個網頁由這些元件構成起來，便成了元件樹 (Component tree)。

{{< image src = "1-1-component-tree.png" caption = "元件樹" >}}


---


## vue2, vue3 有哪些的差異?

> Vue.js 自 3.0 (版本代號：One Piece) 版本開始，除了底層核心由 TypeScript 重寫，也新增了不少特性，這裡簡單列出幾點參考：
> - 引進了 "Fragment" 特性，不再限制元件必須只能是單一根節點
> - 狀態的響應式偵測由 ```Object.defineProperty``` 改為 ```Proxy API```，執行時的效能更好，也解決了過去 Vue 2.x 在物件、陣列更新偵測的問題
> - 模板編譯：靜態節點優化，新的 Virtual DOM 更新時只需要遍歷動態的節點，更新時與實際 DOM 數量脫鉤，減少不必要的效能浪費
> - 內建新增 "Teleport"、"Suspense" 等功能型元件，擴充了更多可能性
> - 新的 Composition API 提供了另一種對程式碼、邏輯甚至是狀態的共用管理方式，擺脫過去 mixins 的混亂
> - 新增 ```setup```、```ref``` 等語法糖，開發時的體驗更好

---


## 用 vue3 寫一個 hello world 需要那些程式碼?

```JavaScript

const { createApp, ref } = Vue; 
    const vm = createApp({ 
    setup () { 
        const message = ref('Hello World!'); 
        return { 
            message 
        } 
    } 
}); 

vm.mount('#app');

```


---



## computed/methods 差別在哪?

> 當定義 computed 之後，其相依的 data 或是 component 中的 props(之後會提到) 改變，computed 也會隨之更新；methods 則是不管資料是否相依都會計算。  
下例的 computed 中沒有相依的 data，因此在 message 被修改時，now 沒有被更新，但 methods 會重新計算更新 getNow 的值。


```html

<div id="app">
  <p>message：{{ message }}</p>
  <p>now (computed)：{{ now }}</p>
  <p>getNow (method)：{{ getNow() }}</p>
</div>

```

---


## html 中 v- 開頭的屬性有什麼用途? 請舉例?
### 模板語法
> **模板語法是邏輯跟頁面之間溝通的媒介**

> - V-text、V-html、V-once ... 等
> - V-text插入：渲染純文字內容
> - V-html：插入整個html結構
> - V-once：將 data 內的內容渲染後，不再追蹤其變化

{{< image src = "v-example.png" caption = "v- 開頭" >}}

---


## 怎麼實作一個按鈕(button)事件?

```html

<div id="example-1">
  <button v-on:click="counter += 1">Add 1</button>
  <p>The button above has been clicked {{ counter }} times.</p>
</div>

```

```JavaScript

var example1 = new Vue({
  el: '#example-1',
  data: {
    counter: 0
  }
})

```

---



## 請舉例一個 v-for 的用途?

> 案例一：陣列渲染
使用v-for迭代渲染出陣列中的元素。如下所示，list 是一個陣列，item 代表用於迭代的元素，使用item.name或item.age可帶出資料的屬性。  
其中第二個參數 index 為資料的索引值 (optional)，由於資料是陣列的形式，因此，依序從 0 開始跑到 2，共 3 筆資料內容。

{{< image src = "v-for-1.png" caption = "v-for" >}}
{{< image src = "v-for-2.png" caption = "渲染結果" >}}


---


## 請用自己的話解釋 vue 元件的 生命週期 (life cycle) 與更新機制?

> 當我們創建好一個 Vue 的實例，就會馬上進入下一個階段beforeCreate()。  
> 1. 初始化顯示階段
>     * beforeCreate() 實例創建前：準備工作：觀察初始化(Observe Data)、初始化事件(Init Events)，這個階段實例的 data、methods 是讀不到的  
>     * created() 實例創建後：這個階段已經完成了資料觀察初始化(data observer)，屬性和方法的運算， watch/event 事件回調。mount 掛載階段還沒開始。
>     * beforeMount() 在掛載開始之前被調用：相關的 render 函數首次被調用。
>     * mounted()：初始化顯示之後。立即調用，是最常用的 callback，用來「掛載」到頁面上。
> 2. 更新狀態顯示階段
>     * beforeUpdate() 資料更新時調用：但不進行 DOM 重新渲染，在資料更新時 DOM 沒渲染前可以在這個生命方法裡進行狀態處理。
>     * updated() 資料更新並且 DOM 重新渲染：這個狀態下資料更新並且 DOM 重新渲染，當這個生命週期方法被調用時，組件 DOM 已經更新，所以這時可以執行依賴於 DOM 的操作。當實例每次進行資料更新時 updated 都會執行。
> 3. 死亡、銷毀 Vue 實例階段
>     * beforeDestory() 實例銷毀之前調用：做收尾的工作，例如清除定時器，否則定時器會一直執行下去
>     * destoryed() 實例銷毀後調用：Vue 實例銷毀後調用。調用後，Vue 實例指示的所有東西都會解綁定，所有的事件監聽器會被移除，所有的子實例也會被銷毀。
---


## 心得

> 除了對JS不太熟悉之外，Vue算是一個蠻好用的框架，在搭建UI時可以利用MVVM將邏輯與畫面給分開，在開發與日後的維護上都較為容易，且我本身在iOS App開發的時候就是使用MVVM，因此在寫Vue的時候可以說是非常得心應手，只要稍加熟悉JS語言的特性，大致上沒有問題！

---