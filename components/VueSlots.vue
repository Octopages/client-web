<template>
  <div>
    <Card color="blue" title="hello" body="Hello World">
      <div slot="title">Title 1 From Slot</div>

      <div slot="body">
        Body 1 From Slot
        <v-text-field placeholder="Ay 7aga 3ashan e7na gamdeen" />
      </div>
    </Card>

    <Card color="red" title="Title 2" body="Body 2" />
    <Card color="green" title="Title 3" body="Body 3" />
    <Card color="brown" />
  </div>
</template>
<script>
import Card from '~/components/Card.vue'
export default {
  components: { Card },
}
</script>
