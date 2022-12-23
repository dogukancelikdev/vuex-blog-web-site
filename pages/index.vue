<template>
    <div>
      <PostList :posts="fetchedPosts" />
      <About />
    </div>  
</template>

<script>
import PostList from '@/components/post/PostList.vue';
import About from '@/components/home/About.vue';
export default {
   components : {
      PostList,
      About,
   },
  // data(){
    //  return{
      //   fetchedPosts : [],
     // }
  // },
   created(){
      //this.$store.dispatch("setPosts",this.fetchedPosts)
   },
   computed : {
      fetchedPosts(){
         return this.$store.getters.getPosts
      }
   },
   //fetch(context){ // tek farkı server tarafından render edilmesi
     // console.log(context)
      //return new Promise((resolve, reject) => {

         //context.store.dispatch("setPosts")
         //resolve()
      //})   
      
      //.catch(e =>  {                                    //resolve basarılı dönüş yaptı 
        // context.error(new Error());  
                                             //reject Başarılı değil
      //})                                   //veritabanından veriyi doğru cekersek then bloğu içi gelir
    //  setTimeout(() => {
      //   callback(null, )
     // },2000)
      
   //},
}
</script>

<style scoped>

</style>