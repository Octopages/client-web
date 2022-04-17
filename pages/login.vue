<template>
  <div>
    <login @success="onSuccess" />
  </div>
</template>

<script>
import Login from '~/components/forms/auth/Login'
export default {
  components: { Login },
  methods: {
    onSuccess(payload) {
      alert(`${payload.email} Logged in Successfully`)
    },
  },
}
</script>
