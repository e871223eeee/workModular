**畫面初始程式碼**
```html
<template>
  <DefaultView :module-key="$route.name" :module-title="title">
    <!-- 程式主體 -->
    <template #search>
      
    </template>
    <!-- 表格 -->
    <template #data-table>

    </template>
  </DefaultView>
</template>


<!-- js -->
<script>
//引入公版
import DefaultView from "@/components/Layout/DefaultLayout.vue";

export default {
  //名稱
  name: "檔案編號",
  components: {
    //定義公版
    DefaultView,
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
 
