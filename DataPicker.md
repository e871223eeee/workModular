**日期元件使用方式**
先在<script>區域引入該元件並定義
```C#
<script>
//引入日期選擇器
import DatePicker from "vue2-datepicker";
export default {
  //名稱
  name: "XXXXX",
  components: {
    //日期選擇器方法
    DatePicker
  },
};
</script>
```
___
使用方式(結合validation)
  - :formatter : yearFormatter/yearMonthFormatter/defaultFormatter(YYYY,YYYY/MM,YYYY/MM/DD)
  - type="格式" : year/month/day(選年,選年月,選年月日)
```html
<div class="form-group required">
  <validation-provider
    v-slot="{ classes, errors }"
    :rules="{ required: true }"
    name="該欄位名稱"
  >
    <Date-Picker
      v-model="綁定的變數 EX:A"
      :input-attr="{ id: '綁定的變數名稱 EX:A' }"
      :input-class="{ ...classes, 'form-control': true }"
      :formatter="顯示的格式"
      placeholder="輸入框內要顯示的文字"
      type="格式"
      output="number"
      class="d-block"
    />
    <span class="text-danger position-absolute">{{ errors[0] }}</span>
  </validation-provider>
</div>
```
