<template> 
<div>

     <img alt="searcher" src="../assets/demo1case.jpg" @click="toggleshow" />
     <model-mask v-if="isShow" :child-is-show="isShow" @update="updateInfo"/>
     <img alt="searcher" src="../assets/demo1case.jpg" />
     <img alt="searcher" src="../assets/demo1case.jpg" />   
     <img alt="searcher" src="../assets/demo1case.jpg" />
     <img alt="searcher" src="../assets/demo1case.jpg" />
     <img alt="searcher" src="../assets/demo1case.jpg" />   
     <img alt="searcher" src="../assets/demo1case.jpg" />
     <img alt="searcher" src="../assets/demo1case.jpg" />
     <img alt="searcher" src="../assets/demo1case.jpg" />   
 
 </div>
 
</template>

<script>
import ModelMask from './ModelMask.vue';

export default {
    name:'Cases',
    data(){
        return{
           isShow:false
        }
    },
    components:{
        ModelMask
    },

     
     methods: {
     toggleshow(){
          this.isShow = !this.isShow;   
         },
         updateInfo(val){
             console.log("父層監聽子層的事件");
             console.log('val=',val);
             this.isShow = !this.isShow;
         }
     }
 
}

</script>

<style>
html.noscroll {
    position: fixed; 
    overflow-y: scroll;
    width: 100%;
}

html.fixWindow {
    position: fixed;
    width: 100%;
}
</style>