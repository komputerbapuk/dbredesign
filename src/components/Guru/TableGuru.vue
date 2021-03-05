<template>
    <v-container-fluid>
    <v-card
        class="d-flex mb-6"
        light
        flat
        tile
      >
        <v-card
          class='mr-auto pa-2'
          flat
          tile
        >
            <v-btn
                depressed
                color="#4380B9"
                rounded
                dark
                class="text-capitalize"
                @click="overlay = !overlay"
            >
            Tambah Guru
            <v-icon
                right
            >
                mdi-plus
            </v-icon>
            </v-btn>
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
                <h4 class="text-center ma-2">Tambah Guru</h4>
                <v-divider></v-divider>
                    <v-container style="width:90%;">
                        <v-text-field
                            label="Nama Guru"
                            rounded
                            background-color="grey lighten-4"
                            height="30px"
                            dense
                        ></v-text-field>
                        <v-text-field
                            label="NIP"
                            background-color="grey lighten-4"
                            rounded
                            height="30px"
                            dense
                        ></v-text-field>
                        <v-select
                            name="jenkel"
                            :items="jeniskelamin"
                            background-color="grey lighten-4"
                            label="Jenis Kelamin"
                            rounded
                            height="30px"
                            dense
                        ></v-select>                                
                        <v-divider></v-divider>

                        <v-card-actions>
                        <v-btn
                            right
                            outlined
                            rounded
                            color="primary"
                            small
                            @click="overlay = false"
                        >
                            Batal
                        </v-btn>
                        <v-btn
                            right
                            dark
                            rounded
                            color="success"
                            small
                        >
                            Simpan
                        </v-btn>
                        </v-card-actions>
                    </v-container>
            </v-card>
            </v-overlay>
            <span class="ml-3">12 Guru</span>
        </v-card>
        <v-card
          class='ml-auto pa-2'
          flat
        >
          <v-text-field
              outlined
              class="rounded-xl"
              v-model="search"
              label="Cari"
              append-icon="mdi-magnify"
              dense
              single-line
              hide-details
          ></v-text-field>
        </v-card>
        <v-card
          class='pa-2'
          flat
          tile
        >
          <v-btn
          depressed
          color="#88B950"
          dark
          rounded
          class="text-capitalize"
          >
            Filter
            <v-icon
                right
                dark
            >
                mdi-filter-outline
            </v-icon>
          </v-btn>
        </v-card>
    </v-card>

    <template>
        <v-data-table
            :headers="headers"
            :items="guru"
            :search="search"
            :items-per-page="5"
            class="elevation-1"
        ></v-data-table>
    </template>
    </v-container-fluid>
</template>
<script>
export default {
    data(){
        return{
            overlay: false,
            search: '',

            headers: [
            {
                class:"green lighten-5 subtitle-1",
                text: 'Nama Guru',
                align: 'start',
                sortable: false,
                
                filterable: true,
                value: 'name',
            },
            { class:"green lighten-5 subtitle-1",text: 'NIP', value: 'nip' },
            { class:"green lighten-5 subtitle-1" ,text: 'Jenis Kelamin', value: 'jenkel' },
            ],

            guru: [
            {
                name: 'Tukiman',
                nip: 392,
                jenkel: 'Laki - laki',
            },
            {
                name: 'Sasha',
                nip: 408,
                jenkel: 'Perempuan',
            },
            {
                name: 'Parman',
                nip: 156,
                jenkel: 'Laki - laki',
            },
            {
                name: 'Parmi',
                nip: 230,
                jenkel: 'Perempuan',
            },
            {
                name: 'Parno',
                nip: 689,
                jenkel: 'Laki - laki',
            },
            {
                name: 'Paiman',
                nip: 227,
                jenkel: 'Perempuan',
            },
            {
                name: 'Killua',
                nip: 129,
                jenkel: 'Laki - laki',
            },
            {
                name: 'Kevin',
                nip: 237,
                jenkel: 'Perempuan',
            },
            {
                name: 'Ichi',
                nip: 169,
                jenkel: 'Laki - laki',
            },
            {
                name: 'Shella',
                nip: 262,
                jenkel: 'Perempuan',
            },
            {
                name: 'Ryan',
                nip: 153,
                jenkel: 'Laki - laki',
            },
            {
                name: 'Rossa',
                nip: 231,
                jenkel: 'Perempuan',
            },
            ],
        }
    }
}
</script>