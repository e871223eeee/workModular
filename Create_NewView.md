**新增資料(跳出新畫面)**
適用於要新增的內容較多時
___
```html
<template>
  <!-- 驗證 -->
  <validation-observer v-slot="{ handleSubmit }" ref="observer">
    <div class="d-flex flex-column min-vh-100 w-100">
      <!-- 標題 -->
      <BreadcrumbHeader
        :items="[{ path: '位置', title: '標題' }, { title }]"
      />
      <!-- 內容 -->
      <section class="mx-7 my-4">
        <!-- 新增/返回 -->
        <div class="row">
          <div class="col mt-2 mb-4">
            <button
              type="button"
              class="btn btn-primary me-2"
              @click="handleSubmit(createHandler)"
            >
              新增
            </button>
            <button
              type="button"
              class="btn btn-link text-decoration-none me-2"
              @click="goBack"
            >
              返回
            </button>
          </div>
        </div>
      </section>
    </div>
  </validation-observer>
</template>

<script>
//引入api模塊
import API from '@/api';
//引入上方標題模塊
import BreadcrumbHeader from '@/components/Util/BreadcrumbHeader.vue';

export default {
  name: '檔名',
  components: {
    //定義上方標題模塊
    BreadcrumbHeader,
  },
  data() {
    return {
      title: '標題(功能)',
      
      //資料(該畫面輸入資料或是要顯示的資料)
      formInput: {
        
      },
      //選項(下拉式選單用)
      options: {
        
      },
    };
  },

  //畫面初始化
  mounted() {
    
  },
  //方法
  methods: {
    //新增
    createHandler() {
      
    },
    //返回
    goBack() {
      this.$router.push(`路徑`);
    },
  },
};
</script>
```
