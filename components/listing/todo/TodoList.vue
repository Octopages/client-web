<template>
  <v-card>
    <v-card-title>
      <slot name="title" :tasks="todoList">Default Title</slot>
    </v-card-title>
    <v-card-text>
      <v-data-table :headers="headers" :items="todoList">
        <div slot="item.done" slot-scope="{ item }">
          <v-switch v-model="item.done" />
        </div>
      </v-data-table>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  data() {
    return {
      headers: [
        { text: 'Task Name', value: 'name' },
        { text: 'Done', value: 'done', sortable: false },
      ],
      todoList: [
        { name: 'Feed The Dog', done: true },
        { name: 'Get Married', done: false },
        { name: 'Eat Food', done: false },
      ],
    }
  },
}
</script>
