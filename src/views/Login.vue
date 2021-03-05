<template>
  <v-app>
    <div class="login">
      <v-container class="fill-height">
        <v-row no-gutters>
          <v-col cols="12" sm="6" md="9">
            <v-img
              class="mx-auto d-block"
              width="70%"
              height="auto"
              contain
              src="../assets/asset siplah/artwork mistar web-01.svg"
            ></v-img>
          </v-col>

          <v-col cols="12" sm="6" md="3">
            <v-card
              flat
              class="mx-auto mt-6 rounded-lg"
              color="white"
              elevation="2"
              height="600px"
            >
              <v-card-title>
                <v-img
                  class="mx-auto"
                  aspect-ratio="1.7"
                  contain
                  max-height="auto"
                  max-width="230"
                  src="../assets/logo mistar/MSTR_BluePax01.png"
                ></v-img>
              </v-card-title>
              <v-card-text class="mt-6">
                <v-form ref="form">
                  <v-text-field
                    class="txtfieldlogin"
                    prepend-inner-icon="mdi-account"
                    v-model="username"
                    :rules="nameRules"
                    required
                    :outlined="outlined"
                    :filled="filled"
                    placeholder="Username"
                    rounded
                    dense
                  >
                  </v-text-field>

                  <v-text-field
                    v-model="password"
                    class="txtfieldlogin"
                    prepend-inner-icon="mdi-key-variant"
                    :append-icon="openclosePassword ? 'mdi-eye' : 'mdi-eye-off'"
                    :rules="passwordRules"
                    :type="openclosePassword ? 'text' : 'password'"
                    @click:append="openclosePassword = !openclosePassword"
                    required
                    placeholder="Password"
                    rounded
                    :outlined="outlined"
                    dense
                    :filled="filled"
                    style="border-color: #ffffff"
                  >
                  </v-text-field>
                  <v-btn
                    class="btnlogin"
                    block
                    rounded
                    dark
                    color="#88B950"
                    x-large
                    :loading="loading"
                    @click="SignIn()"
                    >Login</v-btn
                  >
                </v-form>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>

        <v-snackbar bottom v-model="snackbar" color="red" :timeout="timeout">
          {{ text }}
          <template v-slot:action="{ attrs }">
            <v-btn
              depressed
              icon
              v-bind="attrs"
              @click="snackbar = false"
              small
            >
              <v-icon>mdi-close-circle-outline</v-icon>
            </v-btn>
          </template>
        </v-snackbar>
      </v-container>
    </div>
    <template>
      <v-row justify="space-around">
        <v-col cols="auto">
          <v-dialog
            v-model="dialog"
            transition="dialog-bottom-transition"
            max-width="600"
          >
            <template>
              <v-card>
                <v-toolbar color="primary" class="tlbdevice" dark flat
                  >
                Anda telah aktif di 2 device lainnya ,maksimal login 2 device
                  per user !</v-toolbar
                >
                <v-card-text>
                  <v-row>
                    <v-col cols="12" md="12">
                      <v-simple-table>
                        <thead class="thdevice">
                          <tr>
                            <th>ID Device</th>
                            <th>Nama Device</th>
                            <th>Detail Device</th>
                            <th>Actions</th>
                          </tr>
                        </thead>
                        <tbody class="tbdevice">
                          <tr v-for="device in devices" :key="device.id">
                            <td>{{ device.id }}</td>
                            <td>{{ device.device }}</td>
                            <td>{{ device.device_detail }}</td>
                            <td>
                              <v-checkbox
                                v-model="selecteddevice"
                                :value="device.id"
                              ></v-checkbox>
                            </td>
                          </tr>
                        </tbody>
                      </v-simple-table>
                    </v-col>
                  </v-row>
                </v-card-text>
                <v-card-actions class="justify-end">
                  <v-form>
                    <v-btn
                      color="success"
                      @click="LogoutDevice()"
                        class="btnselesai"
                      depressed
                      >Selesai</v-btn
                    >
                  </v-form>
                </v-card-actions>
              </v-card>
            </template>
          </v-dialog>
          
        </v-col>
      </v-row>
    </template>
  </v-app>
</template>




<script>
import axios from "axios";
import { browserName, osName } from "mobile-device-detect";

export default {
  name: "Login",
  data() {
    return {
      outlined: false,
      filled: true,
      dialog: false,
      loader: null,
      id: [],
      selecteddevice: [],
      loading: false,
      snackbar: false,
      devices: [],
      text: "",
      timeout: 3000,
      openclosePassword: false,
      username: "",
      nameRules: [(v) => !!v || "Username harus di isi"],
      password: "",
      passwordRules: [
        (v) => !!v || "Password harus di isi",
        (v) => (v && v.length >= 6) || "Minimal 6 karakter",
      ],
    };
  },
  methods: {

    SignIn: function () {
      if (this.username == "" || this.password == "") {
        this.snackbar = true;
        this.text = "Username atau Password masih kosong !";
        this.outlined = true;
        this.filled = false;
        this.$refs.form.validate();
      } else {
        this.loader = "loading";
        axios
          .post("https://demo.sistesi.id/api/login", {
            username: this.username,
            password: this.password,
            device: osName,
            device_detail: browserName,
          })
          .then((response) => {
            if (response.data.code == 1) {
             let token = response.data.data.token;
              localStorage.setItem("user-token", token);
              this.$router.push({ path: "/dashboard" }).catch((error) => {
                console.log(error);
              });
            } else {
              const pesan = response.data.data.detail_active;
              this.devices = pesan;
              this.dialog = true;
            }
          })
          .catch((error) => {
            const pesan = error.response.data.message;
            this.snackbar = true;
            this.text = pesan;
          });
      }
    },
    
    LogoutDevice: function () {
      axios.post("https://demo.sistesi.id/api/logout_device", {
        id: this.selecteddevice,
      });
      return this.SignIn(this.loader = "loading",false);
    },

  },
  watch: {
    loader() {
      const l = this.loader;
      this[l] = !this[l];
      setTimeout(() => (this[l] = false), 3000);
      this.loader = null;
    },
  },
};
</script>

<style scoped>
.txtfieldlogin {
  font-family: "Poppins", sans-serif;
  font-weight: 300;
  font-size: 14px;
}
.btnlogin {
  font-family: "Poppins", sans-serif;
  font-weight: 400;
  font-size: 16px;
  text-transform: capitalize;
}
.tlbdevice{
  font-family: "Poppins", sans-serif;
  font-weight: 500;
  font-size: 16px;
}
.thdevice{
  font-family: "Poppins", sans-serif;
  font-weight: 300;
  font-size: 14px;
}.tbdevice{
  font-family: "Poppins", sans-serif;
  font-weight: 300;
  font-size: 14px;
}
.btnselesai{
  font-family: "Poppins", sans-serif;
  font-weight: 400;
  font-size: 16px;
  text-transform: capitalize;
}
</style>