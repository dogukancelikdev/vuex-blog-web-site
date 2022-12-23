<template>
    <PostForm  
    @submit="update($event)"
    :is-update="true" 
    :post="fetchedPost"/>
</template>

<script>
import axios from "axios";
import PostForm from "@/components/admin/PostForm.vue";    
export default {
    components : {
       PostForm,
    },
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