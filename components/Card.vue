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
      type: String, // Number , Boolean , Array , Object , Function
      default: 'red',
      // required: true,
      // validate(val) { return true if valid }
    },
    title: {
      type: String,
      default: 'Title',
    },
    body: {
      type: String,
      default: 'Body',
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
