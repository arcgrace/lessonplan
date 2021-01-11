<template>
     <div class="modelmask" :style="modelStyle" >
       <div class="modelcontainer" @click.self="monitorShow">
         <div class="modelbody">
           <p> 教案展示與詳細資料  </p>
           <iframe width="50%" height="80%" src="https://www.youtube.com/embed/2HwLBiHmXRQ" 
            frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        </div>
        </div>
     </div>
</template>

<script>
export default {
    name:'ModelMask',
    data(){
        return{
           childShow:this.childIsShow,
        }
    },
    props:['child-is-show'],
    computed:{
        modelStyle(){
          return{
            'display':this.childShow? '':'none'
          }
        }
      },
    methods:{
      monitorShow(){
        this.childShow = !this.childShow;
        this.$emit('update',this.childShow);
      }
    },
    mounted(){
        
       var $scrollingDiv = $(".modelmask"); // #scrollingDiv請改成自己要移動的元素
        $scrollingDiv.animate({"marginTop": ($(window).scrollTop()) + "px"},0 );
        $(window).scroll(function(){ 
        $scrollingDiv
          .stop()
          .animate({"marginTop": ($(window).scrollTop()) + "px"},0 );   
        });
   
    },
  

  }


</script>

<style>
.modelmask { 
   position: absolute;
  z-index: 10;
  top:0;
  left: 0;  
  width: 100vw;
  height: 100%;
  display: table;
  background-color:rgba(0, 0, 0, .5); 
  transition: opacity .3s ease;
}
.modelcontainer {
  cursor: pointer;
  display: table-cell;
  vertical-align: middle;
}

.modelbody {
  cursor: auto;
  display: block;
  width: 60vw;
  height:70vh;
  margin: 0 auto;
  padding: 2rem;
  background-color: #fff;
}

</style>