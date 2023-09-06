**列印/清除 按鈕範例**
配合
- [驗證](https://github.com/e871223eeee/workModular/blob/main/vee-validate.md)
- [列印元件](https://github.com/e871223eeee/workModular/blob/main/PrintModal.md)
```html
<!-- 列印/清除 -->
<div class="input-group align-items-end mt-6">
  <div class="me-3">
    <button
      type="button"
      class="btn btn-primary"
      @click="handleSubmit(showPrintModal)"
    >
      列印
    </button>
  </div>
  <div class="me-3">
    <button
      type="button"
      class="btn btn-outline-secondary"
      @click="resetForm"
    >
      清除
    </button>
  </div>
</div>
```
___
script內容
```C#
//方法
methods: {
  //清除資料
  resetForm() {
    this.formInput = {
      AAA: "",
      BBB: "",
      CCC: "",
      DDD:true,
      EEE: "",
      FFF: "",
      GGG: true,
      HHH: 0
    };
  },
  //列印方法
  showPrintModal() {
    this.$refs.PrintModal.modal.show();
  },
  //Xls格式列印
  printXls() {
    window.open(
      
    );
    this.$refs.PrintModal.modal.hide();
  },
  //Odf格式列印
  printOdf() {
    window.open(
      
    );
    this.$refs.PrintModal.modal.hide();
  }
},
```
