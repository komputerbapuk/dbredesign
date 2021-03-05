<template>
  <v-app>
      <v-content>
        <router-view></router-view>
      </v-content>
      <Navbar v-if="!['Login'].includes($route.name)"/>
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
