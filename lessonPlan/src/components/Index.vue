<template>
  <section>
        <Header />   
        <Search />
        <Cases />
        <Footer />
</section>
</template>

<script>
import Header from './Header.vue';
import Search from './Search.vue';
import Cases from './Cases.vue';
import Footer from './Footer.vue';

export default {
    name:'Home',
    components:{
        Header,
        Search,
        Cases,
        Footer
    },
    data(){
       return {
        //    xxxx:xxxxx,
        //    ooooo:oooooo
       }
    },
    mounted(){
        console.log('index mounted');
        fetch('./src/assets/jsons/subject.json')
        .then((res)=>res.json())
        .then((data)=>{
            
        console.log(data[0]);

        
        })

        
    }
}
</script>

<style scoped>
    
</style>