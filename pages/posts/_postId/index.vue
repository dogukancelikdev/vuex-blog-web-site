<template>
    <PostDetail :post="fetchedPost"/>
</template>
<script>
import axios from 'axios';    
import PostDetail from '@/components/post/PostDetail.vue';
export default {
    components : {
        PostDetail
    },
    //this.$route.params._postId  ----->>>>>>>>>> context e es
    asyncData(context) {
        return axios.get("https://kose-yazilari-nuxt-js4-default-rtdb.firebaseio.com/posts/"+ context.params.postId + ".json")
        .then(response => {
            return {
                fetchedPost : response.data
            }
        })
    },
}
</script>