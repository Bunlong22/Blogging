
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
     <v-btn type="submit"  @click="submitForm">Submit</v-btn>
   </v-form>
   </v-card>
   <v-btn type="submit" to="/" style="margin-top: 30px; ">Go back to homepage</v-btn>
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
 