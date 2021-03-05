<template>
  <v-container class="mb-5">
    <FormJenjang/>
  </v-container>
</template>

<script>
import FormJenjang from '../components/Jenjang Sekolah/FormJenjang.vue'

  export default {
    name : 'Jenjang',
    components : {
        FormJenjang
    },
    data: () => ({
      items: ['SMK/SMA', 'SMP', 'SD', 'TK'],
      
      semester: ['1 (Satu)', '2 (Dua)']
    }),
  }
</script>
