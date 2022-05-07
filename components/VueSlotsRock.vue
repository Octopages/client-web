<template>
  <div>
    <CardRock color="green" title="propTitle" body="propBody">
      <div slot="title">Title from slot</div>
      <div slot="body">
        body from slot
        <v-text-field placeholder="Ay 7aga 3ashan e7na gamdeen" />
      </div>
    </CardRock>
    <card-rock color="blue" title="helloprop" body="khaledprop">
      <div slot="body">
        second slot
        <v-text-field placeholder="hello every body" />
      </div>
    </card-rock>
  </div>
</template>

<script>
import CardRock from '~/components/CardRock.vue'
export default {
  components: { CardRock },
}
</script>
