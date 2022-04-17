<template>
  <v-card>
    <v-card-title> Login </v-card-title>
    <v-card-text>
      <v-text-field
        v-model="form.email"
        placeholder="Enter Your Email"
        label="Email"
        type="email"
        outlined
      />
      <p v-if="!isEmailValid">Email Is Required</p>       
      <v-text-field
        v-model="form.password"
        placeholder="Enter Your Password"
        label="password"
        type="password"
        outlined
      />
      
    </v-card-text>    
    <v-card-actions>
      <v-btn :disabled="!isFormValid" color="primary"> Login </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  data() {
    return {
      form: {
        email: '',
        password: '',
      },
    }
  },
  computed: {
    isEmailValid() {
      return this.form.email.length > 0
    },
    isPasswordValid() {
      return this.form.password.length > 0
    },
    isFormValid() {
      return this.isEmailValid && this.isPasswordValid
    },
  },
}
</script>
