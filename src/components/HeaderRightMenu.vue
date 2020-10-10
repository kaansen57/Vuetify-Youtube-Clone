<template>
  <div>
    <v-menu :close-on-content-click="false" :nudge-width="250" offset-x >
      <template v-slot:activator="{ on }" >
        <v-avatar size="40" role="button">
          <img :src="require('../assets/avatar.svg')" v-on="on" />
        </v-avatar>
      </template>
      <v-card width="315" >
        <v-list class="pt-0">
          <v-list-item>
            <v-list-item-avatar>
              <v-avatar size="40">
                <img :src="require('../assets/avatar.svg')" />
              </v-avatar>
            </v-list-item-avatar>
            <v-list-item-content>
              <v-list-item-title class="mt-6">
                <strong>Kaan ŞEN</strong>
              </v-list-item-title>
              <v-list-item-subtitle class="mt-2"
                >Youtube Clone</v-list-item-subtitle
              >
              <a href="#" class="text-decoration-none mt-2">
                <v-list-item-subtitle
                  >Google Hesabınızı Yönetin</v-list-item-subtitle
                ></a
              >
            </v-list-item-content>
          </v-list-item>
        </v-list>
        <v-divider />
        <v-list>
          <a
            href="#"
            class="text-decoration-none"
            v-for="(item, i) in menuItem"
            :key="i"
          >
            <v-list-item class="pl-0 hover">
              <v-list-item-action class="ml-4">
                <v-icon>
                  {{ item.icon }}
                </v-icon>
              </v-list-item-action>
              <v-list-item-title>{{ item.title }} </v-list-item-title>
              <v-switch
                v-model="theme"
                color="red"
                v-if="item.title == 'Karanlık Tema'"
              ></v-switch>
            </v-list-item>
            <v-divider v-if="i == 4"></v-divider>
          </a>
        </v-list>
      </v-card>
    </v-menu>
  </div>
</template>

<script>
export default {
  data: () => ({
    theme: false,
    menuItem: [
      { icon: "mdi-account-box", title: "Kanalınız" },
      { icon: "mdi-currency-usd-circle", title: "Ücretli üyelikler" },
      { icon: "mdi-youtube-studio", title: "YouTube Studio" },
      { icon: "mdi-account-box-multiple", title: "Hesap değiştir" },
      { icon: "mdi-exit-to-app", title: "Oturumu Kapat" },
      { icon: "mdi-brightness-4", title: "Karanlık Tema" },
      { icon: "mdi-cog", title: "Ayarlar" },
      { icon: "mdi-help-circle", title: "Yardım" },
      { icon: "mdi-message-alert", title: "Geri bildirim gönder" },
    ],
  }),
  watch:{
    theme(next){
      this.$vuetify.theme.dark = next;
    }
  }
};
</script>

<style></style>
