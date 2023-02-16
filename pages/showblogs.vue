<!-- 
<template>
  <v-container>
     <h2>All blogs</h2>
 
     <v-spacer style="height: 10px;">

     </v-spacer>
    <v-row>
      <v-col v-for="post in posts" :key="post.id" cols="12" md="4">
       
        <v-card>
          <v-card-title class="text--darken-1">{{ post.title }}</v-card-title>
          <v-card-text>{{ post.content }}</v-card-text>
        </v-card>
    
      </v-col>
            <v-btn text large color="blue" style="margin-left:  45%;" to="/">
    Go back to homepage
   </v-btn>
    </v-row>
  </v-container>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const response = await $axios.get('http://ec2-18-183-190-208.ap-northeast-1.compute.amazonaws.com/entries/');
    return { posts: response.data };
  },
};
</script>
<style>

</style>
 -->
 <template>
  <v-container>
    <v-row>
      <v-col v-for="post in posts" :key="post.id" cols="12" md="4">
        <v-card>
          <v-card-title>{{ post.title }}</v-card-title>
    <v-card-text>{{ post.content }}</v-card-text>
    <v-card-actions>
      <v-btn @click="editPost(post)" style="background-color: green;">Edit</v-btn>
      <v-btn @click="deletePost(post)" style="margin-left: 30px; background-color: red; font">Delete</v-btn>
    </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
    <v-btn type="submit" to="/" style="margin-top: 30px;">Go back to homepage</v-btn>
  </v-container>
</template>

<script>
export default {
  // async asyncData({ $axios }) {
  //   const response = await $axios.get('http://ec2-18-183-190-208.ap-northeast-1.compute.amazonaws.com/entries');
  //   return { posts: response.data };
  // },
  data() {
    return {
      posts: []
    }
  },
  mounted() {
    this.getPosts();
  },
  methods: {
    async getPosts() {
      const response = await this.$axios.get('http://ec2-18-183-190-208.ap-northeast-1.compute.amazonaws.com/entries');
      this.posts = response.data;
    },
    async deletePost(post) {
      await this.$axios.delete(`http://ec2-18-183-190-208.ap-northeast-1.compute.amazonaws.com/entries/${post.id}`);
      const index = this.posts.indexOf(post);
      this.posts.splice(index, 1);
    },
    editPost(post) {
      this.$router.push(`/edit-post/${post.id}`);
    }
  }
};
</script>
<style>
</style>