<template>
  <div class="">
    <InvoiceMenu :spreadsheet="spreadsheet" v-on:selectInvoice="openInvoice"></InvoiceMenu>
    <InvoiceDetail :invoice="invoice" ></InvoiceDetail>
    
  </div>
</template>

<script>

const spreadsheetURL = process.env.VUE_APP_SPREADSHEET;

import Tabletop from 'tabletop'
import InvoiceMenu from '../components/InvoiceMenu.vue'
import InvoiceDetail from '../components/InvoiceDetail.vue'

export default {
  name: 'InvoiceMain',
  components: {
    InvoiceMenu,
    InvoiceDetail
  },
  data() {
    return {
      spreadsheet: [],
      invoice: [],
      selection: []
    };
  },
  props: {
    
  },
  methods: {
    openInvoice: function(d) {
      let vm = this;
      vm.selection.push(d);
      vm.invoice = vm.selection;
      
    },

    init: function () {
      let vm = this;
      Tabletop.init({
        key: spreadsheetURL,
        simpleSheet: false,
        orderby: 'volgnummer',
        parseNumbers: false,
        wanted: ['01', '02'],
        postProcess: function(el) {
            vm.spreadsheet.push(el);
          },
      });
    
    }
  },
  created: function() {
    let vm = this;
    vm.init();
  }
}
</script>

<style scoped lang="scss">

</style>
