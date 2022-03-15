<template>


  <div class="about">
    <h1 class="text-center mt-6">List of Beers i like</h1>

      <div  v-for="beer of beers" :key="beer.id">
            <v-card
            class="mx-auto mt-10 d-flex flex-row"
            max-width="644"
            outlined
          >
            <v-list-item three-line>
              <v-list-item-content>
                <div class="text-overline mb-4">
                  beer
                </div>
                <v-list-item-title class="text-h5 mb-1">
                  {{beer.name}}
                </v-list-item-title>
                <v-list-item-subtitle>{{ beer.description }}</v-list-item-subtitle>
              </v-list-item-content>
              <v-list-item-avatar
                tile
                size="80"
                color="grey"
              ></v-list-item-avatar>
            </v-list-item>        
            </v-card>
      </div>
  </div>
  
</template>


<script>

import axios from "axios";
export default {
  name: "App",
  data() {
    return {
      beers: [],
    };
  },
  async created() {
    try {
      const res = await axios.get(`https://localhost:7062/list/`);
      this.beers = res.data;
    } catch (error) {
      console.log(error);
    }
  },
};


</script> 
