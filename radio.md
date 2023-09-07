**選項按鈕範例**
___
- CustomValue_1 -> 名子有對到就好
- CustomValue_2 -> 綁定的變數名稱
- CustomValue_key -> 名子有對到就好
```html
<div class="input-group">
  <div class="form-group me-3 mb-4">
    <label class="form-label">CustomValue_標題</label>
    <div class="d-flex flex-row align-items-center">
      <div class="form-check me-2">
        <input
          class="form-check-input"
          type="radio"
          name="CustomValue_1"
          id="CustomValue_key_1"
          v-model="formInput.CustomValue_2"
          value="0"
        />
        <label class="form-check-label" for="CustomValue_1"> 全部 </label>
      </div>
      <div class="form-check me-2">
        <input
          class="form-check-input"
          type="radio"
          name="CustomValue_1"
          id="CustomValue_key_2"
          v-model="formInput.CustomValue_2"
          value="1"
        />
        <label class="form-check-label" for="CustomValue_key_2"> 廢料 </label>
      </div>
      <div class="form-check me-2">
        <input
          class="form-check-input"
          type="radio"
          name="CustomValue_1"
          id="CustomValue_key_3"
          v-model="formInput.CustomValue_2"
          value="2"
        />
        <label class="form-check-label" for="CustomValue_key_3"> 非廢料 </label>
      </div>
    </div>
  </div>
</div>
```
___
script內的需要加上的東西
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
