<template>
  <v-container>
    <v-row>
      <v-col cols="12">
        <LoginRock ref="loginrockComponent" @success="onSuccess" />
      </v-col>
      <v-col cols="12" lg="6">
        <v-card color="green">Hello_11</v-card>
      </v-col>
      <v-col cols="12" lg="6">
        <v-card color="yellow">Hello_22</v-card>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="auto">
        <v-card color="green"> Auto Width</v-card>
      </v-col>
      <v-spacer />
      <v-col cols="auto">
        <v-card color="red"> Anothe auto Width</v-card>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
import LoginRock from '~/components/forms/auth/LoginRock'
export default {
  components: { LoginRock },
  methods: {
    onSuccess(payload) {
      // alert(`${payload.email} Loged in successfuly`)
      // alert( `${this.$refs.loginrockComponent.form.email} enta sa7777777`)
      this.$refs.loginrockComponent.login()
    },
  },
}
</script>
