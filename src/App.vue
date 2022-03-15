<template>
  <v-app>
    <v-app-bar dense color="#1d4647"
      app
      dark
    >
      <v-tabs> 
        <v-tab to="/">Home</v-tab> 
         <v-tab to="/beerlist">Beerlist</v-tab> 
        
      </v-tabs>
    
    </v-app-bar>

    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    //
  }),
};
</script>
