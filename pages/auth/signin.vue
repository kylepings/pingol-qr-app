<template>
  <div class="d-flex align-center justify-center" style="height: 100vh;">
    <v-card width="500">
      <h1 class="text-center my-6">Sign In</h1>

      <v-card-text>
        <v-text-field
          outlined
          label="Username"
          prepend-inner-icon="mdi-email-outline"
          variant="outlined"
          single-line
        ></v-text-field>

        <v-text-field
          outlined
          label="Password"
          prepend-inner-icon="mdi-lock-outline"
          type="password"
          variant="outlined"
          single-line
        ></v-text-field>

        <v-btn
          class="text-none mb-4"
          color="primary"
          size="x-large"
          variant="flat"
          block
        >
          Login
        </v-btn>

        <div class="text-center my-4">
          <span>OR</span>
        </div>

        <v-btn
          @click="signinWithGoogle()"
          class="text-none mb-4"
          color="red darken-1"
          size="x-large"
          variant="flat"
          block
        >
          <v-icon left>mdi-google</v-icon>Sign in with Google.
        </v-btn>
        
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
export default {
  layout: "auth",
  middleware: "guest",
  methods:{
    signinWithGoogle(){
      this.$auth.loginWith('google')
    }
  }
}
</script>
