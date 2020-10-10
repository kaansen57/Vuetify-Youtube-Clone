<template>
  <v-navigation-drawer v-model="drawer" app clipped>
    <v-list class="mt-3">
       <v-list-item-group  active-class="red--text text--accent-4" >
            <a href="" class="text-decoration-none"  v-for="(item, i) in menuItems"  :key="i">
              <v-divider v-if="i==3" class="mb-5 mt-5"></v-divider>
              <v-list-item  >
                <v-icon>
                  {{ item.icon }}
                </v-icon>
                <v-list-item-title class="ml-6">
                  {{ item.title }}
                </v-list-item-title>
              </v-list-item>
            </a>
         </v-list-item-group>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
import { eventBus } from "../main";
export default {
  data: () => ({
    drawer: true,
    menuItems: [
      { icon: "mdi-home", title: "Ana Sayfa" ,src:""},
      { icon: "mdi-fire", title: "Trendler",src:"" },
      { icon: "mdi-youtube-subscription", title: "Abonelikler" ,src:""},
      { icon: "mdi-bookshelf", title: "Kitaplık" ,src:""},
      { icon: "mdi-history", title: "Geçmiş" ,src:""},
      { icon: "mdi-youtube", title: "Videolarınız",src:"" },
      { icon: "mdi-clock", title: "Daha sonra izle",src:"" },
      { icon: "mdi-thumb-up", title: "Beğendiğim videolar" ,src:""},
    ],
  }),
  methods: {},
  created() {
    eventBus.$on("drawerOnOff", (drawer) => {
      this.drawer = drawer;
    });
  },
};
</script>

<style scoped>


</style>
