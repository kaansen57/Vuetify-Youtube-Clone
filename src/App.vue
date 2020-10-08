<template>
  <v-app>
      <v-app-bar app clipped-left> 
          <v-app-bar-nav-icon/>
            <v-icon class="mx-4" large>
              mdi-video
            </v-icon>
            <v-toolbar-title class="align-center">
                <span class="title">KS Video</span>
            </v-toolbar-title>
             <v-spacer/>
              <v-text-field class="mt-8" placeholder="Ara..."  solo single-line append-icon="mdi-magnify"></v-text-field>
             <v-spacer/>
             <v-btn icon v-for="(icon,i) in rightTopIcon" :key="i">
               <v-icon>
                 {{icon}}
               </v-icon>
             </v-btn>

            <div>
              <v-menu v-model="menu" :close-on-content-click="false" :nudge-width="250" offset-x >
               <template v-slot:activator="{on}">
                 <v-avatar size="40" >
                   <img :src="avatar" v-on="on">
                 </v-avatar>
               </template>
                <v-card>
                  <v-list class="pt-0">
                    <v-list-item>
                      <v-list-item-avatar>
                        <v-avatar size="40" >
                          <img :src="avatar" >
                        </v-avatar>
                      </v-list-item-avatar>
                      <v-list-item-content>
                        <v-liste-item-title class="mt-6"> <strong>Kaan ŞEN</strong> </v-liste-item-title>
                        <v-liste-item-subtitle class="mt-2">Youtube Clone</v-liste-item-subtitle>
                       <a href="#" class="text-decoration-none mt-2"> <v-liste-item-subtitle >Google Hesabınızı Yönetin</v-liste-item-subtitle></a>
                      </v-list-item-content>
                    </v-list-item>
                  </v-list>
                  <v-divider/>
                  <v-list>
                   <a href="#" class="text-decoration-none" v-for="(item,i) in menuItem" :key="i" >
                      <v-list-item class="pl-0 hover">
                          <v-list-item-action class="ml-4">
                                <v-icon>
                                  {{item.icon}}
                                </v-icon>
                      </v-list-item-action>
                        <v-list-item-title >{{item.title}}</v-list-item-title>
                      </v-list-item>
                    </a> 
                  </v-list>
                  </v-card>  
              </v-menu>
            </div>
      </v-app-bar>
  </v-app>
</template>

<script>
export default {
  name: "App",
  components: {

  },

  data: () => ({
      rightTopIcon : ["mdi-upload","mdi-apps","mdi-bell"],
      menu:false,
      avatar:"https://cdn.iconscout.com/icon/free/png-256/avatar-370-456322.png",
      menuItem:[
        {icon:"mdi-account-box",title:"Kanalınız"},
        {icon:"mdi-currency-usd-circle",title:"Ücretli üyelikler"},
        {icon:"mdi-youtube-studio",title:"YouTube Studio"},
        {icon:"mdi-account-box-multiple",title:"Hesap değiştir"},
        {icon:"mdi-exit-to-app",title:"Oturumu Kapat"},
        {icon:"mdi-cog",title:"Ayarlar"},
      ]
  })
};
</script>

<style >
  .hover:hover{
    background-color: #e2e0e0;
  }
</style>