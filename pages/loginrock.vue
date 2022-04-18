<template>
  <div>
    <LoginRock @success="onSuccess" />
  </div>
</template>
<script>
import LoginRock from '~/components/forms/auth/LoginRock'
export default {
  components: { LoginRock },
  methods: {
    onSuccess(payload) {
      alert(`${payload.email} Loged in successfuly`)
    },
  },
}
</script>
