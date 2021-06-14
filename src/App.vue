<template>
  <v-app>
    <v-container>
      <v-card tile elevation="1" class="mt-5">
        <v-card-tittle>
          <h1>Login</h1>
        </v-card-tittle>
        <v-form v-model="isValid">
          <v-card-text>
            <v-text-field
              :rules="emailRules"
              label="Email"
              prepend-icon="mdi-account-circle"
              v-model="user.email"
            />
            <v-text-field
              :rules="passwordRules"
              label="Password"
              prepend-icon="mdi-lock"
              :type="showPassword ? 'text' : 'password'"
              :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
              @click:append="handleClick"
              v-model="user.password"
            />
          </v-card-text>
          <v-divider></v-divider>
          <v-card-actions>
            <v-btn color="success" @click="handleSubmit" :disabled="!isValid">Login</v-btn>
            <v-btn color="info">Register</v-btn>
          </v-card-actions>
        </v-form>
      </v-card>
    </v-container>
  </v-app>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      showPassword: false,
      user: {
        email: "",
        password: "",
      },
      emailRules: [
        value => value != '' || 'Email is required'
      ],
      passwordRules:[
        value => value != '' || 'Password is required',
        value => value.length <= 8 || 'Maksimal password 8 karakter'
      ],
      isValid: false,
    };
  },
  methods: {
    handleClick() {
      this.showPassword = !this.showPassword;
    },
    handleSubmit() {
      console.log(this.user);
      this.user = {
        email: "",
        password: "",
      };
    },
  },
};
</script>
