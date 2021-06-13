<template>
  <v-app>
    <v-container>
      <v-card tile elevation="1" class="mt-5">
        <v-card-tittle>
          <h1>Login</h1>
          <v-card-text>
            <v-form>
              <v-text-field
                label="Username"
                prepend-icon="mdi-account-circle"
              />
              <v-text-field
                label="Password"
                prepend-icon="mdi-lock"
                :type="showPassword ? 'text' : 'password'"
                :append-icon="showPassword ? 'mdi-eye' :'mdi-eye-off'" @click:append="handleClick"
              />
            </v-form>
          </v-card-text>
          <v-card-actions>
            <v-btn color="success">Login</v-btn>
            <v-btn color="info">Register</v-btn>
          </v-card-actions>
        </v-card-tittle>
      </v-card>
    </v-container>
  </v-app>
</template>

<script>
export default {
  name: "App",
  data(){
    return{
      showPassword:false
    }
  },
  methods:{
    handleClick(){
      this.showPassword = !this.showPassword
    }
  }
};
</script>
