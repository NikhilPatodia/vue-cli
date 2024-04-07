<template>
   <div>
    <div v-if="error">
     {{ error }}
    </div>
    <div v-if="posts.length">
      <PostList v-if="showPost" :posts= "posts"/>
    </div>
    <div v-else>
      Loading...
    </div>
   </div>
   <button @click="showPost = !showPost">Toggle Posts</button>
</template>

<script>
// @ is an alias to /src
import PostList from '@/components/PostList.vue';
import getPosts from '../composables/getPosts.js'
import { ref } from 'vue';
export default {
  name: 'HomeView',
  components:{ PostList },
 setup(){
  const {posts, error, load} = getPosts();
  load()
  let showPost = ref(true);
  return { posts , showPost, error }
 }
}
</script>
