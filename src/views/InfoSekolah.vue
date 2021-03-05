<template>
    <div class="infosekolah mt-16">
         <div class="display-1">Info Sekolah</div>
         <v-card elevation="0" rounded="xl">
         <v-row class="my-3">
             <v-col cols="12"  md="3" sm="3">
                 <Upload />
             </v-col>
             <v-col cols="12"  md="9" sm="9">
                  <Form />
             </v-col>
         </v-row>
         </v-card>
    </div>
</template>

<script>
import Upload from '../components/Info Sekolah/Upload.vue'
import Form from '../components/Info Sekolah/Form.vue'

export default {
    name : 'InfoSekolah',
    components : {
        Upload,
        Form
    }
}
</script>
