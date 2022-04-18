<template>
  <v-container>
    <v-row>
      <v-col cols="12">
        <login ref="loginComponent" @success="onSuccess" />
      </v-col>
      <v-col cols="12" lg="6">
        <v-card color="green">Hello</v-card>
      </v-col>
      <v-col cols="12" lg="6" md="8">
        <v-card color="green">Hello</v-card>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="auto" class="green">Auto Width</v-col>
      <v-spacer />
      <v-col cols="auto" class="red">Another Auto Width</v-col>
    </v-row>
  </v-container>
</template>

<script>
import Login from '~/components/forms/auth/Login'
export default {
  components: { Login },
  mounted() {
    // this.$refs.loginComponent.form.email = 'Bala7';
    this.$refs.loginComponent.login()
  },
  methods: {
    onSuccess(payload) {
      this.$emit('page-success')
    },
  },
}
</script>
