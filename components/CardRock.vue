<template>
  <div :style="{ backgroundColor: color }" class="card">
    <slot name="title">
      <div>{{ title }}</div>
    </slot>

    <slot name="body">
      <div>{{ body }}</div>
    </slot>
  </div>
</template>

<script>
export default {
  props: {
    color: {
      type: String,
      default: 'red',
    },
    title: {
      type: String,
      default: 'Title xx',
    },
    body: {
      type: String,
      default: 'Body xx',
    },
  },
}
</script>
<style scoped>
.card {
  padding: 10px;
  border-radius: 5px;
  margin: 5px;
}
</style>
