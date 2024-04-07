<template>
    <router-link :to="{ name: 'Detail', params: {id: post.id}}" :post = "post">
        <h3> {{ post.title }}</h3>
    
    </router-link>
  
    <span v-for="tag in post.tags" :key="tag">
        #{{ tag }}
    
    </span>

</template>

<script>
 export default{
    props: ['post']
 }
</script>