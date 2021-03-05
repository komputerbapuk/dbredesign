<template>
  <div class="form">
    <v-card elevation="0" class="ma-2" rounded="xl">
      <v-card-text>
        <v-row>
          <v-col cols="12" sm="5" md="12">
            <label style="color: black">Nama Sekolah *</label>
            <v-text-field filled rounded dense></v-text-field>
          </v-col>
          <v-col cols="12" sm="5" md="12">
            <label style="color: black">Alamat Sekolah *</label>
            <div class="d-flex justify-space-around">
              <v-text-field filled rounded dense></v-text-field>
              <v-btn class="ml-10" depressed color="#4380B9" dark elevation="0"
                >Buka Peta</v-btn
              >
            </div>
          </v-col>
  <v-col cols="12" sm="5" md="12">
         
              <Map/>
      
  </v-col>

          <v-col cols="12" sm="5" md="6">
            <label style="color: black">Telepon Sekolah</label>
            <v-text-field filled rounded dense></v-text-field>
          </v-col>
          <v-col cols="12" sm="5" md="6">
            <label style="color: black">Yayasan</label>
            <v-text-field filled rounded dense></v-text-field>
          </v-col>
        </v-row>

         

        <v-card elevation="2" class="mx-auto">
          <v-card-title
            ><h5><b>Link Sosial Media</b></h5></v-card-title
          >
          <v-divider></v-divider>
          <v-card-text>
            <v-row>
              <v-col cols="12" sm="5" md="6">
                <label style="color: black">Facebook</label>
                <v-text-field
                  prepend-icon="mdi-facebook"
                  color="#1F66A8"
                  filled
                  rounded
                  dense
                ></v-text-field>
              </v-col>
              <v-col cols="12" sm="5" md="6">
                <label style="color: black">Youtube</label>
                <v-text-field
                  prepend-icon="mdi-youtube"
                  color="red"
                  filled
                  rounded
                  dense
                ></v-text-field>
              </v-col>
            </v-row>

            <v-row>
              <v-col cols="12" sm="5" md="6">
                <label style="color: black">Twitter</label>
                <v-text-field
                  prepend-icon="mdi-twitter"
                  color="primary"
                  filled
                  rounded
                  dense
                ></v-text-field>
              </v-col>
              <v-col cols="12" sm="5" md="6">
                <label style="color: black">Instagram</label>
                <v-text-field
                  prepend-icon="mdi-instagram"
                  color="purple"
                  filled
                  rounded
                  dense
                ></v-text-field>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>

        <v-card elevation="2" class="mx-auto mt-8">
          <v-card-title
            ><h5><b>Jam Sekolah *</b></h5></v-card-title
          >
          <v-divider></v-divider>
          <v-card-text>
            <v-row>
              <v-col cols="12" sm="5" md="2">
                <v-select
                  rounded
                  dense
                  filled
                  :items="items"
                  label="Tipe *"
                ></v-select>
              </v-col>

              <v-col cols="12" sm="5" md="2">
                <v-select
                  rounded
                  dense
                  filled
                  :items="level"
                  label="Tingkat *"
                ></v-select>
              </v-col>

              <v-col cols="12" sm="5" md="3">
                <v-text-field
                  label="Jam Masuk *"
                  filled
                  rounded
                  dense
                  append-icon="mdi-clock"
                ></v-text-field>
              </v-col>
              <v-col cols="12" sm="5" md="3">
                <v-text-field
                  label="Jam Pulang *"
                  filled
                  rounded
                  dense
                  append-icon="mdi-clock"
                ></v-text-field>
              </v-col>

              <v-col cols="12" sm="5" md="2" class="pa-5">
                <v-btn depressed color="#CACACA"
                  ><v-icon color="#ffffff">mdi-minus-circle</v-icon></v-btn
                >
              </v-col>
            </v-row>
            <v-divider class="mb-4"></v-divider>
            <v-row>
              <v-col cols="12" sm="5" md="2">
                <v-select
                  rounded
                  dense
                  filled
                  :items="items"
                  label="Tipe *"
                ></v-select>
              </v-col>

              <v-col cols="12" sm="5" md="2">
                <v-select
                  rounded
                  dense
                  filled
                  :items="level"
                  label="Tingkat *"
                ></v-select>
              </v-col>

              <v-col cols="12" sm="5" md="3">
                <v-text-field
                  label="Jam Masuk *"
                  filled
                  rounded
                  dense
                  append-icon="mdi-clock"
                ></v-text-field>
              </v-col>
              <v-col cols="12" sm="5" md="3">
                <v-text-field
                  label="Jam Pulang *"
                  filled
                  rounded
                  dense
                  append-icon="mdi-clock"
                ></v-text-field>
              </v-col>

              <v-col cols="12" sm="5" md="2" class="pa-5">
                <v-btn depressed color="primary" dark
                  ><v-icon color="#ffffff">mdi-plus-circle</v-icon></v-btn
                >
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
import Map from '../Info Sekolah/Map.vue'

export default {
  name: "Form",
  components : {
    Map
  },

  data() {
    return {
      items: ["Foo", "Bar", "Fizz", "Buzz"],
      level: ["1", "2", "3", "4"],
    };
  },
};
</script>

<style>
</style>