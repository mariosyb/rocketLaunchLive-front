<template>
  <v-app>
    <v-main>
      <Card/>
      <HelloWorld/>
      
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import Card from './components/Card';

export default {
  name: 'App',

  components: {
    HelloWorld,
    Card
  },

  data: () => ({
    //
  }),
};
</script>
