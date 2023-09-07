**工程編號選擇視窗模塊範例**

先在<script>區域引入該元件並定義
```html
<script>
//引入工程編號選擇視窗模塊
import CaseInput from '@/components/Util/CaseInput.vue';
export default {
  //名稱
  name: "XXXXX",
  components: {
    //定義工程編號選擇視窗模塊
    CaseInput,
  },
};
</script>
```
___
html部分
  - v-model -> 預設綁定的變數(起)
  - :end.sync -> 綁定迄的變數(選填)
  - required -> 輸入驗證(選填)
```html
<!-- 工程編號 -->
<div class="input-group">
  <div class="form-group me-3 mb-4">
    <label class="form-label">工程編號</label>
    <CaseInput
      v-model="formInput.CustomValue_1"
      :end.sync="formInput.CustomValue_2"
      required
    />
  </div>
</div>
```
