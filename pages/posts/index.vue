<template>
  <div class="posts-page">
    <PostList :posts="loadedPosts" />
  </div>
</template>

<script>
import PostList from "@/components/Posts/PostList";

export default {
  components: {
    PostList,
  },
  computed: {
    loadedPosts() {
      return this.$store.getters.loadedPosts;
    },
  },

  // #1 we could use fetch instead of asyncData
  // #2 we could move all logic of asyncData or fetch to store
  // asyncData(context) {
  //   return new Promise((resolve, reject) => {
  //     setTimeout(() => {
  //       resolve({
  //         loadedPosts: [
  //           {
  //             id: "1",
  //             title: "First Post",
  //             previewText: "This is our first post!",
  //             thumbnail:
  //               "https://static.pexels.com/photos/270348/pexels-photo-270348.jpeg",
  //           },
  //           {
  //             id: "2",
  //             title: "Second Post",
  //             previewText: "This is our second post!",
  //             thumbnail:
  //               "https://static.pexels.com/photos/270348/pexels-photo-270348.jpeg",
  //           },
  //         ],
  //       });
  //     }, 1000);
  //     // reject(new Error())
  //   })
  //     .then((data) => {
  //       return data;
  //     })
  //     .catch((e) => {
  //       context.error(e);
  //     });
  //   // calcback
  //   // callback(null, {
  //   //     loadedPosts: [
  //   //       {
  //   //         id: "1",
  //   //         title: "First Post",
  //   //         previewText: "This is our first post!",
  //   //         thumbnail:
  //   //           "https://static.pexels.com/photos/270348/pexels-photo-270348.jpeg"
  //   //       },
  //   //       {
  //   //         id: "2",
  //   //         title: "Second Post",
  //   //         previewText: "This is our second post!",
  //   //         thumbnail:
  //   //           "https://static.pexels.com/photos/270348/pexels-photo-270348.jpeg"
  //   //       }
  //   //     ]
  //   //   });
  //   // }, 1000);
  // },
};
</script>

<style scoped>
.posts-page {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
