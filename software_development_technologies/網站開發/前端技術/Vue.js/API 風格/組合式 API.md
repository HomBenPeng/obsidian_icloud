
## `ref()`
接受一個內部值，返回一個響應式的、可更改的 ref 對象，此對象只有一個指向其內部值的屬性 `.value`。

### 類型

```ts
function ref<T>(value: T): Ref<UnwrapRef<T>>

interface Ref<T> {
	value: T
}
```

### 詳細說明
ref 對象是可更改的，也即是你可以為 `.value` 賦予新的值。它也是響應式的，即所有對 `.value` 的操作都將被追蹤，並且寫操作會觸發與之相關的副作用。
    
如果將一個對象賦值給 ref，那麼這個對象將通過 `reactive()` 轉為具有深層次響應式的對象。這也意味著如果對象中包含了嵌套的 ref，它們將被深層地解包。
    
若要避免這種深層次的轉換，請使用 `shallowRef()` 來替代。

## 範例：響應式變數

```ts
import { ref } from 'vue'

export default {
  // `setup` 是一個特殊的鉤子，專門用於組合式 API。
  setup() {
    const count = ref(0)

    // 將 ref 暴露給模板
    return {
      count
    }
  }
}
```

```html
<div>{{ count }}</div>
```

**注意事項**：
只有最頂層的 ref 屬性才會被解包。，以下 範例

```ts
const count = ref(0) // 可以正確使用，因為count為最頂層的屬性
const object = { id: ref(1) } // 不能正確使用，id不是最頂層屬性
```

**解決方法**：

方法1：將 `id` 解構為頂層屬性
將 `object.id` 解構為頂層屬性 `id`，這樣在模板中將會自動解包。

```ts
const id = object // 將 id 解構為頂層屬性，這樣就可以在模板中使用 id
```

方式2：手動解包
直接在模板中使用 `object.id.value` 來手動解包 `ref` 的值。

```html
<template>
  <p>{{ object.id.value + 1 }}</p> 
</template>
```
