<template>
    <v-container fluid>
      <v-row justify="center" style="margin-left: 430px;">
        <v-col cols="12" md="8" lg="6">
          <h1 class="text-center mb-5">Contact Us</h1>

          <v-card style="margin-top: 20px;">
            <v-card-text>
              <v-form @submit.prevent="submitForm">
                <v-text-field v-model="name" label="Name" required></v-text-field>
                <v-text-field v-model="email" label="Email" required></v-text-field>
                <v-textarea v-model="message" label="Message" required></v-textarea>
                <v-btn type="submit" >Send</v-btn>
              </v-form>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </template>
  
  <script>
  export default {
    data() {
      return {
        name: "",
        email: "",
        message: "",
      };
    },
    methods: {
      submitForm() {
        // Send form data to server here
        console.log('Name:', this.name)
      console.log('Email:', this.email)
      console.log('Message:', this.message)
     
      },
    },
  };
  </script>
  