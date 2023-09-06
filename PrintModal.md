**列印元件使用方式**

先在<script>區域引入該元件並定義
```C#
<script>
//引入列印模塊
import PrintModal from "@/components/Common/modals/PrintModal";
export default {
  //名稱
  name: "XXXXX",
  components: {
    //定義列印模塊
    PrintModal
  },
};
</script>
```
___
將該元件放置於中section中 並且撰寫方法於methods中
```html
<!-- 列印元件視窗 -->
<PrintModal ref="PrintModal" title="列印" :printXls="printXls" :printOdf="printOdf" />
```
```JS
//Xls格式列印
//方法
methods: {
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
}
```
___
元件呼叫方式
```JS
//方法
methods: {
  //列印方法
  showPrintModal() {
    this.$refs.PrintModal.modal.show();
  },
};
</script>
```
