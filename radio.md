**選項按鈕範例**
```html
<div class="row mt-5">
  <div class="col=auto">
    <label class="form-label">
      <span>標題</span>
    </label>
  </div>
</div>
<div class="row">
  <div class="col-auto">
    <div class="form-check me-2">
      <input
        class="form-check-input"
        type="radio"
        name="群組名稱"
        id="isValueTrue"
        v-model="formInput.isValue"
        value="true"
      />
      <label class="form-check-label" for="isValueTrue"> 是 </label>
    </div>
  </div>
  <div class="col-auto">
    <div class="form-check me-2">
      <input
        class="form-check-input"
        type="radio"
        name="群組名稱"
        id="isValueFalse"
        v-model="formInput.isValue"
        value="false"
      />
      <label class="form-check-label" for="isValueFalse"> 否 </label>
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
      isValue:""
    },
  };
},
```
