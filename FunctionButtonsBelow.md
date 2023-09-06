**下方按鈕列範例**
```html
<div class="input-group align-items-end mt-6">
  <div class="me-3">
    <button
      type="button"
      class="btn btn-secondary text-white"
      @click="handleSubmit(createHandler)"
    >
      新增
    </button>
  </div>
  <div class="me-3">
    <button
      type="button"
      class="btn btn-primary"
      @click="handleSubmit(reviseHandler)"
    >
      確認
    </button>
  </div>
  <div class="me-3">
    <button
      type="button"
      class="btn btn-danger"
      @click="handleSubmit(deleteHandler)"
    >
      刪除
    </button>
  </div>
  <div class="me-3">
    <button
      type="button"
      class="btn btn-outline-secondary"
      @click="goBack"
    >
      取消
    </button>
  </div>
</div>
```
___
script部分
```C#
//方法
methods: {
  //新增
  createHandler() {
    console.log(this.formInput);
  },
  //修改
  reviseHandler() {
    console.log(this.formInput);
  },
  //刪除
  deleteHandler() {
    console.log(this.formInput);
  },
  //返回
  goBack() {
    this.$router.push(`路徑`);
  },
},
```
___
