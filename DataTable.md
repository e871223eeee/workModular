**表格使用範例**
___
html部分
1. :columns -> 表格欄位來源
2. :search-params -> 表格資料搜尋參數
3. :search-fx -> 表格搜尋用的參數
4. :operate -> 表格功能(選填)
   - ['create', 'update', 'delete’, ‘copy’]，和cud-fx搭配使用(待補充)
     - 有create則會提供新增的按鈕
     - 有update則會將可以編輯的欄位變成input
     - 有delete則會在第一欄提供checkbox，選中的即可刪除
     - 有copy則會在第二欄提供button，點擊即可複製
   - :show-add-modal="showAddModal" -> 使用這個能自訂義新增方法
5. :multi-page-select -> true/false 是否有選單頁顯示數量功能
6. :default-sort="{ currentSort: 'key1' , sortDir: 'key2' }"
   - key1 -> 排序基準欄位
   - key2 -> ASC/DESC 由小到大/由大到小
7. :dataSource="tableData" -> 用來定義假資料，方便測試
```html
<template #data-table>
  <DataTable
    title="表格標題"
    :columns="columns"
    :search-params="searchParams"
    :search-fx="searchAPI"
    :operate="[]"
  >
  </DataTable>
</template>
```
___
JS部分

要引入"DataTable"模塊並且定義
1. searchParams -> 用來放表格搜尋參數
2. tableData -> 放表格假資料
3. columns -> 表格內容
   - key -> 會依據該值去json搜尋對應數值並顯示
   - title -> 欄位名稱
   - sortable ->是否要有排序(true/flase)
   - link: (data) => `/NSXXX/XXXXX/Details/${data.id}` -> 維護連結(後方要給路由)
4. showAddModal -> 以跳出新畫面的方式讓使用者新增資料

```html
<script>
//引入表格模塊
import DataTable from "@/components/Util/DataTable.vue";

export default {
  //名稱
  name: "NS60703",
  components: {
    //定義公版
    DefaultView,
    //定義時間選擇器
    DatePickerEx,
    //定義表格
    DataTable,
  },
  //資料
  data() {
    return {
      //api的搜尋參數
      searchParams: {},

      //表格假資料
      tableData: [
        { id: 1, roleCorporateUnit: 'D0003 北區', roleYear: '112', roleAdjustDate: '1120812', roleMaterialCode: '114514 下北澤田所浩二' ,roleIsReceive: '領料', roleIsIncrease: '加'},
        { id: 2, roleCorporateUnit: 'D0004 南區', roleYear: '111', roleAdjustDate: '1110715', roleMaterialCode: '114514 惡臭教官厥拉德' ,roleIsReceive: '退料', roleIsIncrease: '減'},
      ],

      //表格內容
      columns: [
        {
          key: "roleCorporateUnit",
          title: "區處",
          sortable: true,
        },
        { 
          key: "roleYear", 
          title: "年度",
          sortable: true,
        },
        { 
          key: "roleAdjustDate", 
          title: "調整日期",
          sortable: true,
        },
        { 
          key: "roleMaterialCode", 
          title: "材料編號",
          sortable: true,
        },
        { 
          key: "roleIsReceive", 
          title: "領退料別",
          sortable: true,
        },
        { 
          key: "roleIsIncrease", 
          title: "增減別",
          sortable: true,
        },
        { 
          key: "roleMaintain", 
          title: "維護",
          link: (data) => `/NS6/0703/Details/${data.id}`,
        },
      ],
    };
  },
  
  //畫面初始化
  mounted() {
  },

  //方法
  methods: {
    //搜尋api
    async searchAPI() {
      
    },

    //搜尋
    searchHandler() {
      this.searchParams = { ...this.formInput };
    },

    //新增
    showAddModal() {
      this.$router.push(`/NS6/0703/Create`);
    },
  },
};
</script>
```
