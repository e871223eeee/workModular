**下拉式選單使用範例**
  - :key ->唯一值 綁變數的鍵值或是直接綁index
  - :value ->索引值 會跟v-model的變數值做交互 如果有初始值會根據該值查詢
  - CustomValue->有此前綴的為需要改的變數
    - CustomValue_標題 -> 標題
    - CustomValue_1 ->兩個位置的名稱有對應到就好
    - CustomValue_2 ->要綁定的變數，變數與畫面顯示同步
    - CustomValue_3 ->下拉式選單內容的變數(json)
    - CustomValue_4 ->鍵值(json)
    - CustomValue_5 ->顯示的內容(json)
___
沒有輸入驗證版本
```html
<div class="form-group me-3 mb-4">
  <div class="row">
    <div class="col-auto">
      <label for="CustomValue_1" class="form-label">CustomValue_標題</label>
    </div>
  </div>
  <div class="row">
    <div class="col-auto">
      <select id="CustomValue_1" v-model="formInput.CustomValue_2" class="form-select">
      <option value="">CustomValue_選單預設值(可不加)</option>
      <option
        v-for="option in options.CustomValue_3"
        :key="option.CustomValue_4"
        :value="option.CustomValue_4"
      >
        {{ option.CustomValue_5 }}
      </option>
    </select>
    </div>
  </div>
</div>
```
___
有輸入驗證的版本
```html
<div class="form-group me-3 mb-4 required">
  <div class="row">
    <div class="col-auto">
      <label for="CustomValue_1" class="form-label">
        <span>區處</span>
        <span class="text-danger">*</span>
      </label>
    </div>
  </div>
  <div class="row">
    <div class="col-auto">
      <validation-provider
        v-slot="{ classes, errors }"
        :rules="{ required: true }"
        name="CustomValue_標題"
      >
        <select
          id="CustomValue_1"
          v-model="formInput.CustomValue_2"
          :class="classes"
          class="form-select"
        >
          <option value="">CustomValue_選單預設值(可不加)</option>
          <option
            v-for="option in options.CustomValue_3"
            :key="option.CustomValue_4"
            :value="option.CustomValue_4"
          >
            {{ option.CustomValue_5 }}
          </option>
        </select>
        <span class="text-danger position-absolute">{{ errors[0] }}</span>
      </validation-provider>
    </div>
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

    //選項(下拉式選單用)
    options: {
      //(假資料)
      selectValueArray: [{id:0, CustomValue_3:"AAA"},{id:1, CustomValue_3:"BBB"},{id:2, CustomValue_3:"CCC"},{id:3, CustomValue_3:"DDD"},{id:4, CustomValue_3:"EEE"},{id:5, CustomValue_3:"FFF"}],
    },
  };
},
```
