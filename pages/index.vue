<template>
    <v-app >
     
  
      <v-content>
        <v-container fluid>
          <v-row align-="center" justify="center">
            <v-col cols="12" sm="8" md="6">
              <h1 class="display-2 text-center">Welcome to the Daily blog!</h1>
              <p class="text-center">
                This is where you can journal everything in your life!
              </p>
            </v-col>
          </v-row>
          <v-spacer></v-spacer>
          <v-img
            src="https://www.verywellmind.com/thmb/5wPtd7WDrA_3NIo6U4MkFl0c2A4=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/GettyImages-995468182-5c12fc3e46e0fb000108d8f4.jpg"
            alt="journal"
          ></v-img>
          <v-row align-="center" justify="center">
            <v-col cols="12" sm="8" md="6">
              <p class="text-center">
                Our DailyBlog misson is to create a safe space for everyone. To
                journal and keep making life easy and better.
              </p>
              <v-row justify="center">
                   <v-btn
                class="mt-5"
                color="primary"
                large
                href="fillin"
              >
                Blogging
              </v-btn>
              </v-row>
           
            </v-col>
          </v-row>
          <v-content>
            <v-col align-="center" justify="center">
              <h2 class="mt-15 text-lg-center">
                Why you should Choose DailyBlog
              </h2>
            </v-col>
            <v-container>
              <v-row>
                <v-col cols="4" class="px-2">
                  <v-img
                    src="https://it.wisc.edu/wp-content/uploads/Secure-Website-900x400.jpg"
                    width="373px"
                    height="200px"
                  />
                  <p class="mt-3 text-lg-center">Secure</p>
                </v-col>
                <v-col cols="4" class="px-2">
                  <v-img
                    src="https://cdn2.vectorstock.com/i/1000x1000/55/76/easy-to-use-rubber-stamp-vector-16575576.jpg"
                    width="373px"
                    height="200px"
                  />
                  <p class="mt-3 text-lg-center">Easy to use</p>
                </v-col>
                <v-col cols="4" class="px-2">
                  <v-img
                    src="https://media.istockphoto.com/id/1156404289/vector/free-3d-speech-bubble-sign.jpg?s=612x612&w=0&k=20&c=my4PkXf-u4HHoW_xGpkQuMHRB8yBQswQ8Xw8U7sakHg="
                    width="373px"
                    height="200px"
                  />
                  <p class="mt-3 text-lg-center">Free to use</p>
                </v-col>
              </v-row>
            </v-container>
          </v-content>
          <v-content>
        <v-container>
          <h2 class="mt-15 text-lg-center">
                Let's Start blogging!
              </h2>
             <v-row justify="center">
                   <v-btn
                class="mt-5"
                color="primary"
                large
                href="fillin"
              >
                Blogging
              </v-btn>
              </v-row>
        </v-container>
      </v-content>
        </v-container>
      </v-content>
      
  
    </v-app>
  </template>
  
  <script>
  export default {
    data() {
      return {};
    }
  };
  </script>
  
  <style>
  .display-2 {
    font-weight: 200;
  }
  .pa-2 {
    padding: 30px;
  }
  </style>
  