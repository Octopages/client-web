<template>
  <div>
    <VueSlots />
  </div>
</template>

<script>
import VueSlots from '~/components/VueSlots.vue'
export default {
  components: { VueSlots },
}
</script>
