<template>
    <v-row
      justify="space-between"
    >
      <div class="display-1 mb-5 mt-16 " >Jenjang Sekolah</div>
      <v-col
        cols="12"
        md="12"
      > 
        <label for="tipesekolah" style="font-size:12px;">Tipe Sekolah*</label>
        <v-select
          name="tipesekolah"
          :items="items"
          background-color="grey lighten-4"
          placeholder="Pilih satu"
          rounded
          dense
          height="40px"
        ></v-select>
      </v-col>

        <v-col
        class="mt-n6"
        cols="12"
        md="12"
        > 
          <label for="website" style="font-size:12px;">Website Sekolah*</label>
          <v-text-field
            name="website"
            background-color="grey lighten-4"
            value="saraswati"
            rounded
            dense
            height="40px"
            suffix=".mistar.co.id"
          ></v-text-field>
        </v-col>

        <v-card
          class="rounded-lg"
          width="100%"
          outlined
        >   
          <v-card-title>
            <div class="title">Tahun Ajaran</div>
          </v-card-title>
          <v-divider width="100%"></v-divider>
          <v-card-text>
            <v-row>
              <v-col
                cols="12"
                md="6"
              >
                <label for="tglmulai" style="font-size:12px;">Tahun 1*</label>
                <v-text-field
                  name="tahun1"
                  background-color="grey lighten-4"
                  rounded
                  dense
                  type="number"
                  min="2000"
                  max="2030"
                  value="2000"
                  height="40px"
                ></v-text-field>
              </v-col>

              <v-col
                cols="12"
                md="6"
              >
                <label for="tahun2" style="font-size:12px;">Tahun 2*</label>
                <v-text-field
                  name="tahun1"
                  background-color="grey lighten-4"
                  rounded
                  dense
                  type="number"
                  min="2000"
                  max="2030"
                  value="2001"
                  height="40px"
                ></v-text-field>
              </v-col
              >
              
              <v-col
                class="mt-n5"
                cols="12"
                md="12"
              > 
                <label for="semester" style="font-size:12px;">Semester*</label>
                <v-select
                  name="semester"
                  :items="semester"
                  background-color="grey lighten-4"
                  placeholder="Pilih satu"
                  rounded
                  dense
                  height="40px"
                ></v-select>
              </v-col>

              
              <v-col
                class="mt-n5"
                cols="12"
                md="6"
              >
                <label for="tglmulai" style="font-size:12px;">Mulai*</label>
                <v-text-field
                  name="tglmulai"
                  background-color="grey lighten-4"
                  rounded
                  dense
                  type="date"
                  height="40px"   
                  
                ></v-text-field>
              </v-col>

              <v-col
                class="mt-n5"
                cols="12"
                md="6"
              >
                <label for="tglselesai" style="font-size:12px;">Selesai*</label>
                <v-text-field
                  name="tglselesai"
                  background-color="grey lighten-4"
                  type="date"
                  rounded
                  dense
                  height="40px"
                ></v-text-field>
              </v-col
              >

            </v-row>  
          </v-card-text>
        </v-card>

    </v-row>
</template>

<script>
export default {

    data: () => ({
      items: ['SMK/SMA', 'SMP', 'SD', 'TK'],

      tahun1: [2001],

      semester: ['1 (Satu)', '2 (Dua)']
    }),
}
</script>
