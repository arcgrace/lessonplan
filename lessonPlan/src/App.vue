<template id="app">
  <div>
    
    <Index />

  </div>
</template>

<script>

import Index from './components/Index.vue'
import ModelMask from './components/ModelMask.vue'
export default {
  name: 'App',
  data(){
    return{
      outerscrolltop:0
    }
  },
  components: {   
    Index,
    ModelMask
  },
  computed:{
    adjustscroll(){
      this.outerscrolltop=this.scrollTop;
      console.log(this.scrollTop);
    }
  },
  mounted(){
    console.log('app mounted');
  }
}
</script>
