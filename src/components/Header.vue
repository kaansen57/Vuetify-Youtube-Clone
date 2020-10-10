<template>
   
    <v-app-bar app clipped-left >
      <v-app-bar-nav-icon @click="drawer()"/>
      <a href="/" class="text-decoration-none ">
      <v-icon class="mx-4" large>
        mdi-youtube-tv
      </v-icon>
         </a>
      <v-toolbar-title class="align-center">
        <span class="title">KS Video</span>
      </v-toolbar-title>
   
      <v-spacer />
      <v-text-field
        class="mt-8"
        placeholder="Ara..."
        solo
        single-line
      ></v-text-field>
      <v-btn large tile>
        <v-icon>
          mdi-magnify
        </v-icon>
      </v-btn>
      <v-spacer />
      <v-btn icon v-for="(icon, i) in rightTopIcon" :key="i" class="mr-3">
        <v-icon>
          {{ icon }}
        </v-icon>
      </v-btn>
     <HeaderRightMenu></HeaderRightMenu>
    </v-app-bar>
</template>

<script>
import {eventBus} from '../main'
import HeaderRightMenu from './HeaderRightMenu'
export default {
  data: () => ({
    rightTopIcon: ["mdi-upload", "mdi-apps", "mdi-bell"],
     drawerMenu : false
  }),
  components:{
    HeaderRightMenu
  },
  methods:{
    drawer(){
      this.drawerMenu = !this.drawerMenu;
      eventBus.$emit("drawerOnOff",this.drawerMenu);

    }
  }
};
</script>

<style></style>
