<template>
    <v-stepper v-model="e1">
      <v-stepper-header>
        <v-stepper-step
          :complete="e1 > 1"
          step="1"
        >
          Jenjang Sekolah
        </v-stepper-step>

        <v-divider></v-divider>

        <v-stepper-step
          :complete="e1 > 2"
          step="2"
        >
          Info Sekolah
        </v-stepper-step>

        <v-divider></v-divider>

        <v-stepper-step step="3"
          :complete="e1 > 3">
          Guru
        </v-stepper-step>

        <v-divider></v-divider>

        <v-stepper-step step="4"
          :complete="e1 > 4">
          Staff
        </v-stepper-step>

        <v-divider></v-divider>

        <v-stepper-step step="5"
          :complete="e1 > 5">
          Kelas
        </v-stepper-step>

        <v-divider></v-divider>

        <v-stepper-step step="6"
          :complete="e1 > 6">
          Siswa
        </v-stepper-step>

        <v-divider></v-divider>

        <v-stepper-step step="7"
          :complete="e1 > 7">
          Mata Pelajaran
        </v-stepper-step>

        <v-divider></v-divider>

        <v-stepper-step step="8">
          Matpel Guru
        </v-stepper-step>
      </v-stepper-header>

      <v-stepper-items class="mt-n16">
        <v-stepper-content step="1">
          
          <Jenjang/>

          <v-divider class="mt-5 my-2"></v-divider>
          <v-card-actions >
            <v-btn 
              text
              @click="dialog = false"
              class="text-capitalize"
            >
              Simpan Draft
            </v-btn>

            <v-spacer></v-spacer>

            <v-btn
              color="primary"
              @click="e1 = 2"
              class="text-capitalize"
            >
              Selanjutnya
            </v-btn>
          </v-card-actions>

        </v-stepper-content>
        

        <v-stepper-content step="2">
          <InfoSekolah/>
          
          <v-divider class="mt-5 my-2"></v-divider>
          <v-card-actions >
            <v-btn 
              text
              @click="dialog = false"
              class="text-capitalize"
            >
              Simpan Draft
            </v-btn>

            <v-spacer></v-spacer>

            <v-btn
              color="primary"
              @click="e1 = 3"
              class="text-capitalize"
            >
              Selanjutnya
            </v-btn>
          </v-card-actions>
        </v-stepper-content>

        <v-stepper-content step="3">
          <Guru/>
          
          <v-divider class="mt-5 my-2"></v-divider>
          <v-card-actions >
            <v-btn 
              text
              @click="dialog = false"
              class="text-capitalize"
            >
              Simpan Draft
            </v-btn>

            <v-spacer></v-spacer>

            <v-btn
              color="primary"
              @click="e1 = 4"
              class="text-capitalize"
            >
              Selanjutnya
            </v-btn>
          </v-card-actions>
        </v-stepper-content>

        <v-stepper-content step="4">
          <Staff/>
          
          <v-divider class="mt-5 my-2"></v-divider>
          <v-card-actions >
            <v-btn 
              text
              @click="dialog = false"
              class="text-capitalize"
            >
              Simpan Draft
            </v-btn>

            <v-spacer></v-spacer>

            <v-btn
              color="primary"
              @click="e1 = 5"
              class="text-capitalize"
            >
              Selanjutnya
            </v-btn>
          </v-card-actions>
        </v-stepper-content>
        
        <v-stepper-content step="5">  
          <Kelas/>
          
          <v-divider class="mt-5 my-2"></v-divider>
          <v-card-actions >
            <v-btn 
              text
              @click="dialog = false"
              class="text-capitalize"
            >
              Simpan Draft
            </v-btn>

            <v-spacer></v-spacer>

            <v-btn
              color="primary"
              @click="e1 = 6"
              class="text-capitalize"
            >
              Selanjutnya
            </v-btn>
          </v-card-actions>
        </v-stepper-content>

        <v-stepper-content step="6">  
          <Siswa/>
          
          <v-divider class="mt-5 my-2"></v-divider>
          <v-card-actions >
            <v-btn 
              text
              @click="dialog = false"
              class="text-capitalize"
            >
              Simpan Draft
            </v-btn>

            <v-spacer></v-spacer>

            <v-btn
              color="primary"
              @click="e1 = 7"
              class="text-capitalize"
            >
              Selanjutnya
            </v-btn>
          </v-card-actions>
        </v-stepper-content>

        <v-stepper-content step="7">
          <MataPelajaran/>
          
          <v-divider class="mt-5 my-2"></v-divider>
          <v-card-actions >
            <v-btn 
              text
              @click="dialog = false"
              class="text-capitalize"
            >
              Simpan Draft
            </v-btn>

            <v-spacer></v-spacer>

            <v-btn
              color="primary"
              @click="e1 = 8"
              class="text-capitalize"
            >
              Selanjutnya
            </v-btn>
          </v-card-actions>
        </v-stepper-content>

        <v-stepper-content step="8">
          <MatpelGuru/>
          
          <v-divider class="mt-5 my-2"></v-divider>
          <v-card-actions >
            <v-btn 
              text
              @click="dialog = false"
              class="text-capitalize"
            >
              Simpan Draft
            </v-btn>

            <v-spacer></v-spacer>

            <v-btn
              color="primary"
              @click="e1 = 1"
              class="text-capitalize"
            >
              Selanjutnya
            </v-btn>
          </v-card-actions>
        </v-stepper-content>

      </v-stepper-items>
    </v-stepper>
</template>

<script>

import Jenjang from '../views/Jenjang.vue'
import InfoSekolah from '../views/InfoSekolah.vue'
import Kelas from '../views/Kelas.vue'
import Guru from '../views/Guru.vue'
import Staff from '../views/Staff.vue'
import Siswa from '../views/Siswa.vue'
import MataPelajaran from '../views/MataPelajaran.vue'
import MatpelGuru from '../views/MatpelGuru.vue'

export default {
    
      name: "Stepper",
      components:{
        InfoSekolah,
        Jenjang,
        Kelas,
        Guru,
        Staff,
        Siswa,
        MataPelajaran,
        MatpelGuru
      },
  data: () => ({
      
      absolute: true,
      overlay2: false,
      overlay:true,
      dialog: false,
      e1: 1,
      items: ['SMK/SMA', 'SMP', 'SD', 'TK'],
      
      semester: ['1 (Satu)', '2 (Dua)']
    }),
}
</script>
