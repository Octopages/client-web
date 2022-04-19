<template>
  <v-card>
    <v-card-title> LoginRock </v-card-title>
    <v-card-text>
      <v-text-field
        v-model="form.email"
        placeholder="Please Enter Your Emain"
        label="Emial"
        type="emial"
        outlined
      />
      <p v-if="!isEmailValid">Email is Required</p>
      <v-text-field
        v-model="form.password"
        placeholder="Please Enter Your Password"
        label="Password"
        type="password"
        outlined
      />
      <p v-if="!isPasswordValid">Password is Required</p>
    </v-card-text>
    <v-card-actions>
      <v-btn>Cancel</v-btn>
      <v-spacer />
      <v-btn :disabled="!isFormValid" color="primary" @click="loginWithEmit">
        Login
      </v-btn>
      <v-btn>Register</v-btn>
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
      return this.form.password.length > 5
    },
    isFormValid() {
      return this.isEmailValid && this.isPasswordValid
    },
  },
  methods: {
    login() {
      if (this.isFormValid) alert(' loged successfuly ya 5aloda')
      else alert(' Something wrong')
    },
    loginWithEmit() {
      if (this.isFormValid) {
        this.$emit('success', this.form)
      } else this.$emit('failed')
    },
  },
}
</script>
