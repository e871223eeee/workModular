**日期元件使用方式**
先在<script>區域引入該元件並定義
```C#
<script>
//引入時間選擇器模塊
import DatePickerEx from "@/components/Util/DatePickerEx.vue";

export default {
  //名稱
  name: "XXXXX",
  components: {
    //定義時間選擇器模塊
    DatePickerEx,
  },
};
</script>
```

___
- CustomValue_1 : 名子有對到就好
  - CustomValue_2 : 綁定的變數名稱
  - CustomValue_3 : 輸出格式
    - yearFormatter : YYY
    - yearFormatter : YYY/MM
    - defaultFormatter : YYY/MM/DD
  - CustomValue_4 : 選單格式
    - year : 選年
    - month : 選年月
    - 直接不填該欄位: 選年月日
___
沒有輸入驗證版本
```html
<div class="input-group">
  <div class="form-group me-3 mb-4">
    <label for="CustomValue_1" class="form-label">CustomValue_選擇器標題</label>
    <DatePickerEx
      v-model="formInput.CustomValue_2"
      :input-attr="{ id: 'CustomValue_1' }"
      :input-class="{ 'form-control': true }"
      :formatter="CustomValue_3"
      placeholder="CustomValue_未輸入時顯示"
      output="number"
      type="CustomValue_4"
      class="d-block"
    />
  </div>
</div>
```
___
輸入驗證版本
```html
<div class="input-group">
  <div class="form-group me-3 mb-4 required">
    <label for="CustomValue_1" class="form-label">CustomValue_選擇器標題</label>
    <validation-provider
      v-slot="{ classes, errors }"
      :rules="{ required: true }"
      name="CustomValue_選擇器標題"
    >
      <DatePickerEx
        v-model="formInput.CustomValue_2"
        :input-attr="{ id: 'CustomValue_1' }"
        :input-class="{ ...classes, 'form-control': true }"
        :formatter="CustomValue_3"
        placeholder="CustomValue_未輸入時顯示"
        type="CustomValue_4"
        output="number"
        class="d-block"
      />
      <span class="text-danger position-absolute">{{ errors[0] }}</span>
    </validation-provider>
  </div>
</div>
```
___
資料範例
script內的需要加上的東西範例
```C#
//資料
data() {
  return {
    //資料
    formInput: {
      CustomValue_2:""
    },
  };
},
```
