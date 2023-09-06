**一般輸入框範例**
 - CustomValue->有此前綴的為需要改的變數
    - CustomValue_標題 ->標題
    - CustomValue_1 ->兩個位置的名稱有對應到就好
    - CustomValue_2 ->要綁定的變數，變數與畫面顯示同步
 ___
沒有輸入驗證的版本
```html
<div class="input-group">
  <div class="form-group me-3 mb-4">
    <label for="CustomValue_1" class="form-label">CustomValue_標題</label>
    <input
      id="CustomValue_1"
      v-model="formInput.CustomValue_2"
      type="text"
      class="form-control"
    >
  </div>
</div>
```
___
 有輸入驗證的版本
```html
<div class="input-group">
  <div class="form-group me-3 mb-4 required">
    <label for="CustomValue_1" class="form-label">CustomValue_標題</label>
    <validation-provider
    v-slot="{ classes, errors }"
    name="CustomValue_標題"
    :rules="{ required: true }"
    >
      <input
        id="CustomValue_1"
        v-model="formInput.CustomValue_2"
        type="text"
        class="form-control"
        :class="classes"
      >
      <span class="text-danger position-absolute">{{ errors[0] }}</span>
    </validation-provider>
  </div>
</div>
```
___

script內的需要加上的東西範例
```C#
//資料
data() {
  return {
    //資料(該畫面輸入資料或是要顯示的資料)
    formInput: {
      CustomValue_2:""
    },
  };
},
```
