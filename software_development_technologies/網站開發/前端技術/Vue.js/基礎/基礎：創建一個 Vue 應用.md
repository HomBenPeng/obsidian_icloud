建立日期時間：2025 / 01 / 25

## `createApp` 函數
**說明：** 每個 Vue 應用均通過[`createApp`](https://zh-hk.vuejs.org/api/application.html#createapp)函數來創建一個新的 **應用實例**。
- **功能：** 創建一個應用實例。
- **類型：**

```javascript
	function createApp(rootComponent: Component, rootProps?: object): App
```
- **詳細訊息**
	- 第一個參數（rootComponent）：傳入根組件
	- 第二個參數（rootProps）：
		- 可選
		- 傳遞給根組件的 props
- **示例**

	1.  直接連結根組件
	
	```javascript
		import { createApp } from 'vue'
	
		const app = createApp({
		  /* 根组件选项 */
		})
	```
	
	2. 從別處導入根組件
	
	```javascript
		import { createApp } from 'vue'
		import App from './App.vue'
		
		const app = createApp(App)
	```

## 根組件
- 根組件通常是你的應用程序的最外層組件，作為整個應用程序的起點。這個根組件一般會掛載（mount）到一個在 HTML 文件中的 DOM 元素上，從而初始化 Vue 應用。
- 傳入 `createApp` 的對象實際上是一個組件，每個應用都需要一個“根組件”，其他組件將作為其子組件。

## 掛載應用
- 應用實例必須在調用了 `.mount()` 方法後才會渲染出來。該方法接收一個“容器”參數，可以是一個實際的 DOM 元素或是一個 CSS 選擇器字符串：

```html
	<div id="app"></div>
```

```javascript
	app.mount('#app')
```

- **注意事項：**
	- `.mount()` 方法應該始終在整個應用配置和資源註冊完成後被調用。同時請注意，不同於其他資源註冊方法，它的返回值是根組件實例而非應用實例。

## 應用配置
應用實例會暴露一個 `.config` 對象來允許我們配置一些應用級的選項，例如定義一個應用級的錯誤處理器，用來捕獲所有子組件上的錯誤：

```javascript
	app.config.errorHandler = (err) => {
	/* 處理錯誤 */
	}
```

應用實例還提供了一些方法來註冊應用範圍內可用的資源，例如註冊一個組件：

```javascript
	app.component('TodoDeleteButton', TodoDeleteButton)
```

這讓 `TodoDeleteButton` 在應用的任何地方都是可用的。