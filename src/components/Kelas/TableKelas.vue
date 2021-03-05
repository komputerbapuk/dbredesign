<template>
    <v-data-table
        :headers="headers"
        :items="siswa"
        :search="search"
        :items-per-page="5"
        class="elevation-1"
    ></v-data-table>
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
            text: 'Nama Kelas',
            align: 'start',
            sortable: false,
            
            filterable: true,
            value: 'name',
          },
          { class:"green lighten-5 subtitle-1",text: 'NIP', value: 'nip' },
          { class:"green lighten-5 subtitle-1" ,text: 'Jenis Kelamin', value: 'jenkel' },
        ],
        siswa: [
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
        
        jeniskelamin: ['Laki - laki', 'Perempuan'],
    }
  }
}
</script>