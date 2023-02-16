<!-- <template>
    <v-container class="fill-height">
      <v-container>
    <v-card class="mt-6">
      <v-card-title>
        New Post
      </v-card-title>
      <v-card-text>
        <v-form>
          <v-text-field v-model="title" label="Title"></v-text-field>
          <v-textarea v-model="content" label="Content"></v-textarea>
        </v-form>
      </v-card-text>
      <v-card-actions>
        <v-btn color="blue" @click="newPost" to="/about">Submit</v-btn>
      </v-card-actions>
    </v-card>
  </v-container>
    </v-container>
  </template>
  
  
  <script>
  export default {
    
    
    data() {
    return {
      title: "",
      content: "",
    };
  },
  methods: {
    async newPost() {
      const response = await this.$axios.post(
        "http://ec2-18-183-190-208.ap-northeast-1.compute.amazonaws.com/entries",
        { title: this.title, content: this.content }
      );
      // handle response
    },
  },
  computed: {
    posts() {
      return this.$store.state.posts;
    },
  },
  async fetch() {
    await this.$store.dispatch("fetchPosts");
  },
  }
  </script>
   -->
   <template>
   <v-container class="fill-height">
    <v-container>
      <v-card class="mt-6">
      <v-card-title>
        New Blog
      </v-card-title>
    <v-form @submit.prevent="submitForm">
      <v-text-field v-model="title" label="Title" ></v-text-field>
      <v-textarea v-model="content" label="Content"></v-textarea>
      <v-btn type="submit" >Submit</v-btn>
    </v-form>
    </v-card>
    <v-btn type="submit" to="/" style="margin-top: 30px;">Go back to homepage</v-btn>
    </v-container>
    </v-container>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        title: '',
        content: ''
      };
    },
    methods: {
      async submitForm() {
        try {
          const response = await axios.post('http://ec2-18-183-190-208.ap-northeast-1.compute.amazonaws.com/entries', {
            title: this.title,
            content: this.content
          });
          this.$store.commit('addCard', response.data);
        } catch (error) {
          console.error(error);
        }
      }
    }
  };
  </script>
  