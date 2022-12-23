<template>
    <PostForm @submit="savePost($event)"/> <!--o formdan gelen verileri almak için event-->
</template>

<script>
import axios from 'axios';  
import PostForm from "@/components/admin/PostForm.vue";    
export default {
    components : {
       PostForm,
    },
    methods : {
        savePost(post){
           this.$store.dispatch("addPost",post)
           .then(response => {
            this.$router.push("/admin")
           })
        }
    }
}
</script>