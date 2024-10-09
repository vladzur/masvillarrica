<template>
  <v-app>
    <v-navigation-drawer v-model="drawer">
      <v-list nav>
        <v-list-item to="/">
          <v-item-title>
            <v-slot prepened>
              <v-icon>mdi-home</v-icon>
            </v-slot>
            Inicio
          </v-item-title>
        </v-list-item>
        <v-list-item to="/user">
          <v-item-title>
            <v-slot prepened>
              <v-icon>mdi-account</v-icon>
            </v-slot>
            Usuario
          </v-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-app-bar-title>Más Villarrica</v-app-bar-title>
    </v-app-bar>

    <v-main>
      <RouterView />
    </v-main>
    <v-footer>
      <span>&copy; {{ year }}</span>
    </v-footer>
  </v-app>
</template>

<script setup>
import { ref } from 'vue'
import { RouterView } from 'vue-router';
const drawer = ref(null)
const year = new Date().getFullYear()
</script>
