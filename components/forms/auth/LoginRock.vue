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
      {{ validCounter }}
      <br />
      {{ namechanges }}
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
      validCounter: 0,
      names: ['ahmed', 'ali', 'khaled'],
      namechanges: 0,
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
  watch: {
    isFormValid() {
      if (this.isFormValid === true) {
        this.validCounter += 1
      }
    },
    names: {
      deep: true,
      handler() {
        this.namechanges += 1
      },
    },
  },
  methods: {
    login() {
      if (this.isFormValid) alert(`logged successfuly ya ${this.form.email}`)
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
