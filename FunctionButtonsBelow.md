**下方按鈕列範例**
```html
<div class="input-group align-items-end mt-6">
  <div class="me-3">
    <button
      type="button"
      class="btn btn-secondary text-white"
      @click="handleSubmit()"
    >
      新增
    </button>
  </div>
  <div class="me-3">
    <button
      type="button"
      class="btn btn-primary"
      @click="handleSubmit()"
    >
      確認
    </button>
  </div>
  <div class="me-3">
    <button
      type="button"
      class="btn btn-danger"
      @click="handleSubmit()"
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
