<template>
  <v-app-bar app clipped-left>
    <MobileSearchInput v-show="searchButton"></MobileSearchInput>

    <v-app-bar-nav-icon @click="drawer()" class="d-none d-sm-flex" />
    <a href="/" class="text-decoration-none ">
      <v-icon
        class="mx-4"
        large
        color="red darken-3 "
        v-text="'mdi-youtube-tv'"
      ></v-icon>
    </a>
    <v-toolbar-title class="align-center">
      <span class="title ">KS Video</span>
    </v-toolbar-title>

    <v-spacer />

    <v-text-field
      class="mt-8 mr-3 d-none d-sm-flex"
      placeholder="Ara"
      outlined
      dense
      prepend-inner-icon="mdi-magnify"
    ></v-text-field>

    <!-- web/masaüstü tasarım butonu  -->
    <v-btn class="d-none d-sm-flex" icon :loading="loadingButton()">
      <v-icon v-text="'mdi-movie-search'"></v-icon>
    </v-btn>

    <v-spacer />

    <!-- mobil tasarım butonu -->
    <v-btn @click="searchBtn()" class="d-flex d-sm-none mr-5" icon>
      <v-icon v-text="'mdi-movie-search'"></v-icon>
    </v-btn>

    <v-btn
      icon
      v-for="(icon, i) in rightTopIcon"
      :key="i"
      class="mr-3 d-none d-sm-flex"
    >
      <v-icon v-text="icon"> </v-icon>
    </v-btn>
    <HeaderRightMenu></HeaderRightMenu>
  </v-app-bar>
</template>

<script>
import { eventBus } from "../main";
import HeaderRightMenu from "./HeaderRightMenu";
import MobileSearchInput from "./MobileSearchInput";
export default {
  data: () => ({
    rightTopIcon: ["mdi-upload", "mdi-apps", "mdi-bell"],
    drawerMenu: false,
    searchButton: false,
    loading: false,
  }),
  components: {
    HeaderRightMenu,
    MobileSearchInput,
  },
  methods: {
    drawer() {
      this.drawerMenu = !this.drawerMenu;
      eventBus.$emit("drawerOnOff", this.drawerMenu);
    },
    searchBtn() {
      this.searchButton = !this.searchButton;
      eventBus.$emit("searchButton", this.searchButton);
    },
    loadingButton() {
      this.loading = true;
      setTimeout(() => {
        this.loading = false;
      }, 2000);
    },
  },
  computed: {},
  created() {
    eventBus.$on("searchButton", (searchBtnEvent) => {
      this.searchButton = searchBtnEvent;
    });
  },
};
</script>

<style scoped>
.search-btn {
  height: 38px !important;
  width: 20px !important;
}
.v-input__control {
  height: 32px !important;
}
</style>
