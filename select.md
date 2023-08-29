**下拉式選單使用範例**
結合輸入驗證
  - :key ->唯一值 綁變數的鍵值或是直接綁index
  - :value ->索引值 會跟v-model的變數值做交互 如果有初始值會根據該值查詢

```html
<validation-provider 
  name="單位名稱" 
  :rules="{ required: true }" 
  v-slot="{ classes, errors }"
  >
  <select class="form-select" :class="classes" v-model="formInput.selectValue">
    <option value="">初始顯示文字(可不加)</option>
    <option
      v-for="dataValue in options.selectValueArray"
      :key="dataValue.id"
      :value="dataValue.id"
    >
      {{ dataValue.name }}
    </option>
  </select>
  <span class="text-danger h-24 position-absolute">{{ errors[0] }}</span>
</validation-provider>
```
___
script內的需要加上的東西
```C#
//資料
data() {
  return {
    //資料(該畫面輸入資料或是要顯示的資料)
    formInput: {
      selectValue:""
    },

    //選項(下拉式選單用)
    options: {
      //(假資料)
      selectValueArray: [{id:0, name:"AAA"},{id:1, name:"BBB"},{id:2, name:"CCC"},{id:3, name:"DDD"},{id:4, name:"EEE"},{id:5, name:"FFF"}],
    },
  };
},
```
