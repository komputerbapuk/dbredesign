<template>
  <div>
    <v-app-bar 
      flat 
      color="white" 
      fixed
      dense
      >

      <v-toolbar-title>
          <img src="../assets/logo mistar/MSTR_BluePax02.png" alt="mistar logo" height="30px" class="mt-2">
      </v-toolbar-title>

      <v-spacer></v-spacer>
      <v-menu
        left
        bottom
        offset-y
      >
        <template v-slot:activator="{ on, attrs }">
          <v-btn 
            color="white"
            depressed
            v-bind="attrs"
            v-on="on"
            >
            <span 
            class="mr-2 text--secondary text-capitalize">Admin Siplah</span>
            <v-avatar size="26">
              <img
                src="https://cdn.vuetifyjs.com/images/john.jpg"
                alt="John"
              >
            </v-avatar>
          </v-btn>
        </template>

      </v-menu>
    </v-app-bar>
    <v-divider></v-divider>

     <v-spacer></v-spacer>

    <v-navigation-drawer floating permanent app width="200px" style="margin-top:95px;">

      <v-list
        dense
        nav
        
      >
        <v-list-item 
          v-for="item in items"
          :key="item.title"
          router :to="item.route"
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        
        <v-list-item @click="Logout()">
          <v-list-item-icon>
            <v-icon>
              mdi-power
            </v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>
              Logout
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>

        <v-footer padless light class="white">
          <v-col
            class="text-center"
            cols="12"
            style="margin-top:150px;"
          >
            <span class="text--secondary" style="font-size:10px;">Copyright Mistar {{ new Date().getFullYear() }}</span>
          </v-col>
        </v-footer>
      </v-list>
    </v-navigation-drawer>
    
  </div>
</template>

<script>
import axios from 'axios';
  export default {
    data () {
      return {
        items: [
          { title: 'Dashboard', icon: 'home', route:'/dashboard' },
          { title: 'Jenjang Sekolah', icon: 'widgets', route :'/jenjang' },
          { title: 'Info Sekolah', icon: 'info', route :'/infosekolah' },
          { title: 'Guru', icon: 'mdi-account', route :'/guru' },
          { title: 'Staff', icon: 'mdi-account-multiple', route :'/staff' },
          { title: 'Kelas', icon: 'mdi-home-variant', route :'/kelas' },
          { title: 'Siswa', icon: 'mdi-human-child', route :'/siswa' },
          { title: 'Mata Pelajaran', icon: 'mdi-book-multiple', route :'/matapelajaran' },
          { title: 'Matpel Guru', icon: 'mdi-clipboard-text', route :'/matpelguru' }
        ],
        right: null,
      }
    },
    methods:{
      Logout: function(){
        const token = localStorage.getItem("user-token");
        axios
          .post("https://demo.sistesi.id/api/logout",[], {
            headers: {
              'Authorization': "Bearer " + token,
            },
          })
          .then(()=>{
            localStorage.removeItem("user-token");
            this.$router.push({path: "/login"})
          });
      }
    }
  }
</script>
