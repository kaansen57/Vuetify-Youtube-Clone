<template>
  <v-app>
    <Content/>
    <Header/>
    <NavigationMenu/>
    <BottomNavigation />
  </v-app>
</template>

<script>
import Header from "./components/Header";
import Content from "./components/Content";
import NavigationMenu from "./components/NavigationMenu";
import BottomNavigation from "./components/BottomNavigation";
export default {
  name: "App",
  components: {
    Header,
    Content,
    NavigationMenu,
    BottomNavigation,
  },

  data: () => ({
    rightTopIcon: ["mdi-upload", "mdi-apps", "mdi-bell"],
    menu: false,
    drawer: true,
    menuItem: [
      { icon: "mdi-account-box", title: "Kanalınız" },
      { icon: "mdi-currency-usd-circle", title: "Ücretli üyelikler" },
      { icon: "mdi-youtube-studio", title: "YouTube Studio" },
      { icon: "mdi-account-box-multiple", title: "Hesap değiştir" },
      { icon: "mdi-exit-to-app", title: "Oturumu Kapat" },
      { icon: "mdi-cog", title: "Ayarlar" },
    ],
  }),
  methods: {},
};
</script>

<style>
.hover:hover {
  background-color: #e2e0e0;
}
</style>
