<template>
  <v-main >
    <v-container  >
      <v-row class="mt-5">
        <v-col cols="6" sm="6" md="4" lg="3" xl="2"  v-for="(item, i) in videos" :key="i"  >
          <a href="" class="text-decoration-none">
            <v-card width="260" :height="height" tile>
              <v-img
                width="260"
                height="145"
                :lazy-src="`https://picsum.photos/10/6?imaage=${i + 1}`"
                :src="`https://picsum.photos/500/300?imaage=${i + 1}`"
              ></v-img>

              <v-card-title>
                <div>
                <v-avatar size="35" class="mr-2 ">
                  <img :src="require('../assets/avatar.svg')" />
                </v-avatar>
                  {{ item.title }}
                 </div>
              </v-card-title>
              <v-card-subtitle class="mt-1">
                {{ item.sharing }} <br />
                {{ item.views + " Görüntüleme - " + item.date }}
              </v-card-subtitle>
            </v-card>
          </a>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<script>
export default {
  data: () => ({
    videos: [
      {
        id: 0,
        img: "",
        title: "Vue Js ve Vuetify ",
        sharing: "Kaan ŞEN",
        views: 50,
        date:
          new Date().getDate() +
          "/" +
          new Date().getMonth() +
          "/" +
          new Date().getFullYear(),
      },
      {
        id: 1,
        img: "",
        title: "Vue Js ile Vuetify",
        sharing: "Kaan ŞEN",
        views: 50,
        date:
          new Date().getDate() +
          "/" +
          new Date().getMonth() +
          "/" +
          new Date().getFullYear(),
      },
      {
        id: 2,
        img: "",
        title: "Vue Js ile Vuetify",
        sharing: "Kaan ŞEN",
        views: 50,
        date:
          new Date().getDate() +
          "/" +
          new Date().getMonth() +
          "/" +
          new Date().getFullYear(),
      },
      {
        id: 3,
        img: "",
        title: "Vue Js ile Vuetify",
        sharing: "Kaan ŞEN",
        views: 50,
        date:
          new Date().getDate() +
          "/" +
          new Date().getMonth() +
          "/" +
          new Date().getFullYear(),
      },
      {
        id: 4,
        img: "",
        title: "Vue Js ile Vuetify",
        sharing: "Kaan ŞEN",
        views: 50,
        date:
          new Date().getDate() +
          "/" +
          new Date().getMonth() +
          "/" +
          new Date().getFullYear(),
      },
      {
        id: 5,
        img: "",
        title: "Vue Js ile Vuetify",
        sharing: "Kaan ŞEN",
        views: 50,
        date:
          new Date().getDate() +
          "/" +
          new Date().getMonth() +
          "/" +
          new Date().getFullYear(),
      },
      {
        id: 6,
        img: "",
        title: "Vue Js ile Vuetify",
        sharing: "Kaan ŞEN",
        views: 50,
        date:
          new Date().getDate() +
          "/" +
          new Date().getMonth() +
          "/" +
          new Date().getFullYear(),
      },
      {
        id: 7,
        img: "",
        title: "Vue Js ile Vuetify",
        sharing: "Kaan ŞEN",
        views: 50,
        date:
          new Date().getDate() +
          "/" +
          new Date().getMonth() +
          "/" +
          new Date().getFullYear(),
      },
      {
        id: 8,
        img: "",
        title: "Vue Js ile Vuetify",
        sharing: "Kaan ŞEN",
        views: 50,
        date:
          new Date().getDate() +
          "/" +
          new Date().getMonth() +
          "/" +
          new Date().getFullYear(),
      },
      {
        id: 9,
        img: "",
        title: "Vue Js ile Vuetify",
        sharing: "Kaan ŞEN",
        views: 50,
        date:
          new Date().getDate() +
          "/" +
          new Date().getMonth() +
          "/" +
          new Date().getFullYear(),
      },
      {
        id: 10,
        img: "",
        title: "Vue Js ile Vuetify",
        sharing: "Kaan ŞEN",
        views: 50,
        date:
          new Date().getDate() +
          "/" +
          new Date().getMonth() +
          "/" +
          new Date().getFullYear(),
      },
      {
        id: 11,
        img: "",
        title: "Vue Js ile Vuetify",
        sharing: "Kaan ŞEN",
        views: 50,
        date:
          new Date().getDate() +
          "/" +
          new Date().getMonth() +
          "/" +
          new Date().getFullYear(),
      },
    ],
    height: 280
  }),
  methods:{
    
  },
  mounted(){
    if(this.$vuetify.breakpoint.width < 600) {
      this.height = 350;
    }
  }
};
</script>

<style scoped>
</style>
