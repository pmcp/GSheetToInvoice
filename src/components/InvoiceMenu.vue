<template>
  <div class="menu">
       <div v-for="d in spreadsheet" @click="selectInvoice(d)" :key="d.volgnummer">{{d.volgnummer}} - {{d.client}}</div>
  </div>
</template>

<script>

export default {
  name: 'InvoiceMenu',
  props: [
    'spreadsheet'
  ],
   methods: {
    selectInvoice: function(d) {
      let vm = this;
      vm.$emit('selectInvoice', d);
    },
  
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.menu {
    @media print {
        display: none;
    }
}

</style>
