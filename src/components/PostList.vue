<template>

   <div v-for="post in posts" :key="post.id">
       <SinglePost :post = "post"/>
   </div>


</template>



<script>
import { onMounted, onUnmounted } from 'vue';
import SinglePost from './SinglePost.vue';

export default{
    props: ['posts'],
    components: { SinglePost },
    setup(){
        onUnmounted(()=>{
            console.log("Componenet UnMounted")
        }),
        onMounted(()=>{
            console.log("Component Mounted")
        })
    }
}


</script>