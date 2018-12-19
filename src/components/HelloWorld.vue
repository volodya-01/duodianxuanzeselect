<template>
  <div class="hello">
<selectdemo/>
<select2/>
<!-- <Table2/> -->
  </div>
</template>

<script>
import selectdemo from '@/components/selectdemo'
import select2 from '@/components/select2'
/* import Table2 from '@/components/Table2' */
export default {
  name: 'HelloWorld',
  components:{
    selectdemo,
    select2
 /*    Table2 */
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
