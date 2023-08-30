**搜尋/清除按鈕範例**
___
html部分
```html
<!-- 搜尋/清除 -->
<div class="row mt-2 mb-4">
  <div class="col-auto">
    <button type="button"
      class="btn btn-primary me-2"
      @click="searchHandler">
      搜尋
    </button>
    <button
      type="button"
      class="btn btn-link text-decoration-none"
      @click="clearHandler"
    >
      清除
    </button>
  </div>
</div>
```
___
script部分
```C#
//資料
data() {
  return {
    //資料
    formInput: {},

    //搜尋結果
    searchParams: {},
  };
},

//方法
methods: {
  // 搜尋
  searchHandler() {
    this.searchParams = { ...this.formInput };
  },

  // 清除
  clearHandler() {
    //清除資料
    this.formInput = {}
  },
},
```
