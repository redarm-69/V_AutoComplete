# V_AutoComplete

A Vue.js plugin/component for auto-complete input functionality.  
Vue.js 自動完成輸入框元件/插件。

---

## Features 功能特色

- Lightweight and easy to use
- Highly customizable suggestion list
- Supports keyboard navigation
- Easy integration with external APIs or local data

- 輕量且易於使用
- 建議清單高度自訂化
- 支援鍵盤操作
- 可輕鬆串接外部 API 或本地資料

---

## Installation 安裝

```bash
npm install @redarm-69/v-autocomplete
```

或

```bash
yarn add @redarm-69/v-autocomplete
```

---

## Usage 用法

### Register Component 註冊元件

```javascript
import Vue from 'vue'
import VAutoComplete from '@redarm-69/v-autocomplete'

Vue.use(VAutoComplete)
```

### In Template 在模板中使用

```vue
<v-auto-complete
  :suggestions="mySuggestions"
  v-model="selectedValue"
  placeholder="Type to search..."
/>
```

#### Props 屬性

| Prop           | Type      | Description                   | 屬性        | 類型      | 說明             |
|----------------|-----------|-------------------------------|-------------|-----------|------------------|
| suggestions    | Array     | List of suggestions           | suggestions | 陣列      | 建議清單         |
| v-model        | String    | Selected value                | v-model     | 字串      | 選取的值         |
| placeholder    | String    | Input placeholder             | placeholder | 字串      | 輸入框提示文字   |
| ...            | ...       | ...                           | ...         | ...       | ...              |

---

## Example 範例

```javascript
data() {
  return {
    mySuggestions: ['Apple', 'Banana', 'Orange'],
    selectedValue: ''
  }
}
```

---

## License 授權

MIT

---

## Author 作者

[redarm-69](https://github.com/redarm-69)
