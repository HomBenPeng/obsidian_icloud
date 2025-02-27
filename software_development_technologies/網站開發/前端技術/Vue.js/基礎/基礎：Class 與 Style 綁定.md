數據綁定的一個常見需求場景是操縱元素的 CSS class 列表和內聯樣式。因為 `class` 和 `style` 都是元素属性，我們可以和其他属性一樣使用 `v-bind` 將它們和動態的字符串綁定。但是，在處理比較複雜的綁定時，通過拼接生成字符串是麻煩且易出錯的。因此，Vue 專門為 `class` 和 `style` 的 `v-bind` 用法提供了特殊的功能增強。除了字符串外，表達式的值也可以是對象或數組。

---
###  綁定 HTML class
#### 綁定對象
綁定class `:class`（`v-bind:class` 的縮寫）傳遞一個對象來動態切換 class

##### 一般的 data 屬性設定

```javascript
export default {
  data() {
    return {
	    isActive: true, 
        hasError: false,
        activeClass: 'active',
        errorClass: 'text-danger'
    }
  }
};
```

##### data 屬性設定一個物件

```javascript
export default {
  data() {
    return {
		classObject: {
			active: true,
			'text-danger': false
		}
    }
  }
};
```

##### 計算屬性設定返回對象

```javascript
data() {
  return {
    isActive: true,
    error: null
  }
},
computed: {
  classObject() {
    return {
      active: this.isActive && !this.error,
      'text-danger': this.error && this.error.type === 'fatal'
    }
  }
}
```

##### 綁定 class 各式寫法範例

```html
<!-- 以下範例 active 是否存在取決於 isActive 的布林值 -->
<div :class="{ active: isActive }"></div>

<!-- 可以綁定多個 class 對多個 class 進行操作 -->
<!-- :class 指令可以與一般的 class 屬性共存 -->
<div
  class="static"
  :class="{ active: isActive, 'text-danger': hasError }"
></div>
<!-- 以上範例渲染結果 -->
<div class="static active"></div>

<!-- 邦定一個物件 -->
<div :class="classObject"></div>
<!-- 渲染以上範例的結果 -->
<div class="active"></div>

<!-- 邦定一個陣列渲染多個 CSS class -->
<div :class="[activeClass, errorClass]"></div>
<!-- 以上範例渲染結果 -->
<div class="active text-danger"></div>

<!-- 從陣列中有條件地渲染某個 class，你可以使用三元表達式 -->
<div :class="[isActive ? activeClass : '', errorClass]"></div>
<!-- 以上範例也可改寫成如下 -->
<div :class="[{ activeClass: isActive }, errorClass]"></div>
```

---

###  在組件上使用
對於只有一個根元素的組件，當你使用了 `class` 屬性時，這些 class 會被添加到根元素上並與該元素上已有的 class 合併。

##### 建立組件 `MyComponent`

```html
<!-- 子組件模板 class 原始就宣告了 foo bar -->
<p class="foo bar">Hi!</p>
```

##### 在根組件使用 `MyComponent` 組件

```html
<!-- 在使用組件時 使用子組件 class 添加 baz boo -->
<MyComponent class="baz boo" />
```

##### 渲染的結果

```html
<!-- 渲染後的 class 合併了子組件與根組件的 class  -->
<p class="foo bar baz boo">Hi!</p>
```

##### 在根組件使用子組件綁定class

```html
<MyComponent :class="{ active: isActive }" />
```

##### 渲染的結果

```html
<p class="foo bar active">Hi!</p>
```

---

###  綁定 style 樣式

```javascript
export default {
  data() {
    return {
	    activeColor: 'red', 
	    fontSize: 30,
	    styleObject: { 
		    color: 'red', 
		    fontSize: '13px' 
	    }
    }
  }
};
```

##### 綁定 style 各式寫法範例

```html
<div :style="{ color: activeColor, fontSize: fontSize + 'px' }"></div>

<!-- kebab-cased 形式的 CSS 屬性 key寫法（(對應其 CSS 中的實際名稱） -->
<div :style="{ 'font-size': fontSize + 'px' }"></div>

<!-- 直接綁定一個物件，可以讓程式碼更簡潔 -->
<div :style="styleObject"></div>

<!-- 綁定陣列 -->
<div :style="[baseStyles, overridingStyles]"></div>
```

##### 自動前綴
 當綁定 style 中使用了需要瀏覽器特殊前綴的 CSS 屬性時，Vue 會自動為他們加上相應的前綴。Vue 是在運行時檢查該屬性是否支持在當前瀏覽器中使用。如果瀏覽器不支持某個屬性，那麼將嘗試加上各個瀏覽器特殊前綴，以找到哪一個是被支持的。

##### 樣式多值
你可以對一個樣式屬性提供多個 (不同前綴的) 值，舉例來說：

```html
<div :style="{ display: ['-webkit-box', '-ms-flexbox', 'flex'] }"></div>
```

數組僅會渲染瀏覽器支持的最後一個值。在這個示例中，在支持不需要特別前綴的瀏覽器中都會渲染為 `display: flex`。