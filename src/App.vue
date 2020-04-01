<template>
  <v-app>
    <Navbar />
    <v-content>
      <div class="mx">
        <router-view></router-view>
      </div>
    </v-content>
    
  </v-app>
</template>

<script>
import Navbar from './components/Navbar';

export default {
  name: 'App',

  components: {
    Navbar,
  },

  data: () => ({
    //
  }),
};
</script>

<style scoped>
  main.v-content {
    padding: 1rem 1.5rem !important;
  }
</style>