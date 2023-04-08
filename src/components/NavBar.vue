<template>
    <v-app>
      <v-app-bar app color="#993366" dark>
    <!-- show nav only on mobile -->
    <v-container class="d-flex container">
        <v-app-bar-nav-icon class="d-md-none" @click="drawer = !drawer" color="white"></v-app-bar-nav-icon>

    <!-- a link in vuetify -->
        <v-btn href="/" class="my-btn" :ripple="false" id="no-background-hover" ><v-img
        contain
        height="50"
        width="50"
        src="@/assets/logo.png"
        alt="logo" class="no-hover my-btn"
      /></v-btn>
    </v-container>

        <v-spacer></v-spacer>
        <div class="d-none d-md-flex" v-for="(item, index) in items" :key="index" >
            <v-btn color="white" text>{{ item.title }}</v-btn>
        </div>
        
      </v-app-bar>
      <v-navigation-drawer v-model="drawer" class="d-md-none" app>
        <v-list>
          <v-list-item v-for="(item, index) in items" :key="index" @click="drawer = false">
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
      <v-main>
        <v-container>
          <!-- Main content of the page goes here -->
        </v-container>
      </v-main>
    </v-app>
  </template>

<style scoped lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Della+Respira:300,400,700&display=swap');
.my-btn:hover {
  color: #993366 ;
}

html {
    font-family: 'Della Respira', serif !important;
}
</style>
  
  <script lang="ts">
  export default {
    data() {
      return {
        drawer: false,
        items: [
          { title: "Home" },
          { title: "About" },
          { title: "Contact" },
        ],
        pageTitle: "Dr. Alaro"
      };
    },
    mounted() {
      document.title = this.pageTitle;
    }
  };
  </script>



  