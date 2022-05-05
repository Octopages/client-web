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
      {{ namesChanges }}
    </v-card-text>
    <v-card-actions>
      <v-btn>Cancel</v-btn>
      <v-spacer />
      <v-btn>Register</v-btn>
      <v-btn :disabled="!isFormValid" color="primary" @click="login"
        >Login</v-btn
      >
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
      validCounter: 0,
      names: ['ahmed', 'mohamed', 'khaled'],
      namesChanges: 0,
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
  watch: {
    isFormValid() {
      if (this.isFormValid === true) {
        this.validCounter += 1
      }
    },
    names: {
      deep: true, // if you are watching arrays or json object
      handler() {
        // the callback function to be executed on change
        this.namesChanges += 1
      },
    },
  },
  methods: {
    login() {
      if (this.isEmailValid) {
        this.$emit('success', this.form)
      } else this.$emit('failed')
    },
  },
}
</script>
