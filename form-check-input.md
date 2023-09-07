**勾選框範例**
___
- CustomValue_1 : 名子有對到就好
- CustomValue_2 : 綁定的變數名稱
```html
<input
  class="form-check-input ms-5"
  type="checkbox"
  id="CustomValue_1 Check"
  v-model="formInput.CustomValue_2"
/>
<label class="form-check-label ms-2" for="CustomValue_1 Check">
  CustomValue_標題
</label>
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
      CustomValue_2:true,
    },
  };
},
```
