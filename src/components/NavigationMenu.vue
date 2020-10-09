<template>
  <v-navigation-drawer v-model="drawer" v-on:dra="draw($event)" app clipped>
    <v-list>
      <v-row class="ma-2 mb-3">
        <v-icon>
          mdi-video
        </v-icon>
        <v-toolbar-title class="">
          <span class="title"> Navigation Bar</span>
        </v-toolbar-title>
      </v-row>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
    data:() => ({
        drawer : true
    }),
  methods: {
    draw() {
        
    },
  },
};
</script>

<style></style>
