<template>
    <v-app>
      <v-app-bar app color="primary" dark>
    <!-- show nav only on mobile -->
        <v-app-bar-nav-icon class="d-md-none" @click="drawer = !drawer"></v-app-bar-nav-icon>


        <v-toolbar-title>My App</v-toolbar-title>
        <v-spacer></v-spacer>
        <div class="d-none d-md-flex">
        <v-btn text>Home</v-btn>
        <v-btn text>About</v-btn>
        <v-btn text>Contact</v-btn>
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
      };
    },
  };
  </script>
  