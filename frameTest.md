**畫面初始程式碼**
___
基礎畫面
```html
<template>
  <DefaultLayout :module-key="$route.name" :module-title="title">
    <!-- 程式主體 -->
    <template #search> </template>
    <!-- 表格 -->
    <template #data-table> </template>
  </DefaultLayout>
</template>


<!-- js -->
<script>
//引入公版模塊
import DefaultLayout from "@/components/Layout/DefaultLayout.vue";

export default {
  //名稱
  name: "檔案編號",
  components: {
    //定義公版模塊
    DefaultLayout,
  },
  //資料
  data() {
    return {
      title: "標題名稱",

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
  },
};
</script>
```
___
有列印/清除的畫面
```html
<template>
  <DefaultLayout :module-key="$route.name" :module-title="title">
    <!-- 程式主體 -->
    <template #search>
      <!-- 驗證 -->
      <validation-observer v-slot="{ handleSubmit }">
        <!-- 列印元件視窗 -->
        <PrintModal
          ref="PrintModal"
          title="列印"
          :printXls="printXls"
          :printOdf="printOdf"
        />
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
      </validation-observer>
    </template>
    <!-- 表格 -->
    <template #data-table> </template>
  </DefaultLayout>
</template>

<!-- js -->
<script>
//引入公版模塊
import DefaultLayout from '@/components/Layout/DefaultLayout.vue';
//引入列印模塊
import PrintModal from '@/components/Common/modals/PrintModal';
export default {
  //名稱
  name: '頁面編號',
  components: {
    //定義公版模塊
    DefaultLayout,
    //定義列印模塊
    PrintModal,
  },
  //資料
  data() {
    return {
      title: '標題',

      //資料(該畫面輸入資料或是要顯示的資料)
      formInput: {},

      //選項(下拉式選單用)
      options: {},
    };
  },

  //畫面初始化
  mounted() {},

  //方法
  methods: {
    //清除資料
    resetForm() {
      this.formInput = {
        //初始預設值
      };
    },
    //列印方法
    showPrintModal() {
      this.$refs.PrintModal.modal.show();
    },
    //Xls格式列印
    printXls() {
      window.open();
      this.$refs.PrintModal.modal.hide();
    },
    //Odf格式列印
    printOdf() {
      window.open();
      this.$refs.PrintModal.modal.hide();
    },
  },
};
</script>

```
 
