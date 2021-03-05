<template>
  <div class="upload">
    <v-card elevation="0" class="ma-2" rounded="xl" >
      <v-card-title class="justify-center" >
        <v-avatar tile color="#f2f2f2" size="250">
          <v-btn fab color="#ffffff" depressed>
            <v-icon x-large color="#E2E2E2"> mdi-plus </v-icon>
          </v-btn>
        </v-avatar>
      </v-card-title>
      <v-card-subtitle class="text-center mt-3" style="font-size:12px;">
        Logo Sekolah Minimal resolusi foto <br>300 x 300 px
      </v-card-subtitle>
      <v-card-text>
        <center>
          <v-slider v-model="slider.val" :color="slider.color" style="width:200px;"></v-slider>
        </center>
        <div class="d-flex justify-space-around">
          <v-btn fab elevation="1"  small><v-icon>mdi-rotate-left</v-icon></v-btn>
          <v-btn fab elevation="1"  small><v-icon>mdi-rotate-right</v-icon></v-btn>
        </div>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
export default {
  name: "Upload",
  data() {
    return {
      slider: { val: 25, color: "#88B950" },
    };
  },
};
</script>

<style>
</style>