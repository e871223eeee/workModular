**材料選擇元件範例**
先在<script>區域引入該元件並定義
```C#
<script>
//引入材料選擇視窗模塊
import MaterialInput from '@/components/Util/MaterialInput.vue';
export default {
  //名稱
  name: "XXXXX",
  components: {
    //定義材料選擇視窗模塊
    MaterialInput,
  },
};
</script>
```
___
-CustomValue->有此前綴的為需要改的變數
 -CustomValue_標題 ->標題
 -CustomValue_1 ->要綁定的變數，變數與畫面顯示同步
___
沒有輸入驗證版本
```html
<!-- 材料編號 -->
<div class="form-group me-3 mb-4">
  <label class="form-label">CustomValue_標題</label>
  <MaterialInput v-model="formInput.CustomValue_1"/>
</div>
```
___
輸入驗證版本
```html
<!-- 材料編號 -->
<div class="form-group me-3 mb-4 required">
  <label class="form-label">CustomValue_標題</label>
  <MaterialInput v-model="formInput.CustomValue_1"/>
</div>
```
