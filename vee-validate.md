**參考網站 本篇內容來自該網站 個人方便觀看 詳細能至該網站查看**
https://hackmd.io/@hexschool/ryMpt1cmD
___
1. 建立 validation-provider 元件：
    - rules 帶上驗證的規則，規則列表可參考。注意：規則之間不需要帶上空白鍵。
    - v-slot 帶上預計回傳的回饋內容，常用的可參考下方範例，完整列表可參考
1. 建立 input 欄位內容
1. 將回饋帶至驗證（v-slot 的內容）
```html
<validation-provider rules="required|email" v-slot="{ errors }">
  <!-- 輸入框 -->
  <label for="email">Email</label>
  <input id="email" type="email" name="email" v-model="email"
      class="form-control">
  <!-- 錯誤訊息 -->
  <span>{{ errors[0] }}</span>
</validation-provider>
```
備註：v-slot 稱為插槽（Vue 的元件語法之一），可以將驗證結果的回饋資料直接帶入於區塊中，相關概念可參考：
https://cn.vuejs.org/v2/guide/components-slots.html#作用域插槽
___
加入樣式，JavaScript 加入 Bootstrap 樣式設定，可使用以下設定
```html
// Class 設定檔案
VeeValidate.configure({
  classes: {
    valid: 'is-valid',
    invalid: 'is-invalid',
  }
});
```
___
將 HTML 的部分進行更新
1. v-slot 增加 classes
1. input 增加 :class="classes"

```html
<validation-provider rules="required|email" v-slot="{ errors, classes }">
  <!-- 輸入框 -->
  <label for="email">Email</label>
  <input id="email" type="email" name="email" v-model="email"
    class="form-control" :class="classes">
  <!-- 錯誤訊息 -->
  <span class="invalid-feedback">{{ errors[0] }}</span>
</validation-provider>
```
___
**為完整表單進行驗證**
建立 validation-observer 元件：v-slot 帶上預計回傳的回饋內容，常用的可參考下方範例
```html
<validation-observer v-slot="{ invalid }">
</validation-observer>
```
___
加入 form 標籤及 button 標籤：
1. 表單送出改為使用 form submit 的方法
1. 送出表單使用 submit 的方法，如果驗證未通過則 disabled 該按鈕

```html
<!-- validation-observer 驗證整體表單 -->
<validation-observer v-slot="{ invalid }">
  <!-- 表單送出改為使用 form submit 的方法 -->
  <form @submit.prevent="submitForm">
    <validation-provider rules="required|email" class="form-group" tag="div" v-slot="{ errors, classes, passed }">
      ...
    </validation-provider>
    <!-- 送出表單使用 submit 的方法，如果驗證未通過則 disabled 該按鈕 -->
    <button type="submit" class="btn btn-primary" :disabled="invalid">送出表單</button>
  </form>
</validation-observer>
```
___
**使用 JS 觸發驗證**
1.v-slot 加入 handleSubmit
1.表單送出改為 handleSubmit(自訂方法)
```html
<validation-observer v-slot="{ handleSubmit }">
  <form @submit.prevent="handleSubmit(submitForm)">
    ...
    <button type="submit" class="btn btn-primary">送出表單</button>
  </form>
</validation-observer>
```
___
**完整範例**
html
```html
<div id="app" class="container">
  <validation-observer v-slot="{ invalid, handleSubmit }">
    <form @submit.prevent="handleSubmit(submitForm)">
      <validation-provider rules="required|email" class="form-group" tag="div" v-slot="{ errors, classes, passed }">
        <!-- 輸入框 -->
        <label for="email">Email</label>
        <input id="email" type="email" name="email" v-model="email"
               class="form-control" :class="classes">
        <!-- 錯誤訊息 -->
        <span class="invalid-feedback">{{ errors[0] }}</span>
        <span v-if="passed" class="valid-feedback">Email 正確</span>
      </validation-provider>
      <button type="submit" class="btn btn-primary">送出表單</button>
    </form>
  </validation-observer>
</div>
```

JS
```JS
// 將 VeeValidate input 驗證工具載入 作為全域註冊
Vue.component('ValidationProvider', VeeValidate.ValidationProvider);
// 將 VeeValidate 完整表單 驗證工具載入 作為全域註冊
Vue.component('ValidationObserver', VeeValidate.ValidationObserver);

// Class 設定檔案
VeeValidate.configure({
  classes: {
    valid: 'is-valid',
    invalid: 'is-invalid',
  }
})

const app = new Vue({
  el: '#app',
  data: {
    email: '',
    password: ''
  },
  methods: {
    submitForm() {
      console.log('送出表單')
    }
  },
  created() {
    console.log(this);
  }
});
```

