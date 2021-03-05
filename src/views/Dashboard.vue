<template>
  <v-container-fluid>
    <h1 class="ma-5 mt-16">Selamat sore, Admin SMK Saraswati Salatiga!</h1>
  <v-row
    align="center"
    justify="center"
  >
      <v-row justify="center">
        <v-overlay
          :absolute="absolute"
          :value="overlay"
        >
          <v-card 
              light
              class="mx-auto"
              max-width="344"
              outlined
          >
              <h4 class="text-center my-4 font-weight-bold text--secondary">Data Sekolah</h4>
              <v-divider></v-divider>
                  <v-container style="width:90%;" class="pa-5">  
                    <center>                    
                      <v-icon
                        size="140"
                        color="#4380B9"
                      >
                        mdi-folder-open
                      </v-icon>
                      <p class="font-weight-regular text--secondary">Hai Sobat Mistar data sekolahmu masih kosong nih, yuk lengkapi dulu.</p>
                      <v-divider></v-divider>
                      <v-card-actions>
                      <v-dialog 
                        v-model="dialog" 
                        width="1300px"
                      >
                        <template v-slot:activator="{ on, attrs }">
                          <v-btn
                              right
                              dark
                              rounded
                              color="success"
                              small
                              class="text-capitalize font-weight-light"
                              v-bind="attrs"
                              v-on="on"
                          >
                              Selanjutnya
                          </v-btn>
                        </template>

                        <v-card>

                            <!-- Stepper components -->
                            <Stepper/>
                        
                        </v-card>

                      </v-dialog>
                      </v-card-actions>
                    </center>
                  </v-container>
          </v-card>
        </v-overlay>
      </v-row>
  </v-row>
  </v-container-fluid>
</template>

<script>
  
import Stepper from '../components/Stepper.vue'

  export default {
    data: () => ({
      
      absolute: true,
      overlay2: false,
      overlay:true,
      dialog: false,
      e1: 1,
      items: ['SMK/SMA', 'SMP', 'SD', 'TK'],
      
      semester: ['1 (Satu)', '2 (Dua)']
    }),
    name : 'Dashboard',
    components : {
        Stepper
    }
  }
</script>