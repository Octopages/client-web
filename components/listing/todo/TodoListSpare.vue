<template>
  <v-card>
    <v-card-title>
      <slot name="title" :tasks="todolist"> Default title</slot>
    </v-card-title>
    <v-card-text>
      <v-data-table :headers="headers" , items="todolist">
        <div slot="item.done" slot-scope="item">
          <v-switch v-model="item.done"></v-switch>
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
      todolist: [
        { name: 'wake up late', done: true },
        { name: 'drink some coffe', done: false },
        { name: 'kill some one', done: true },
      ],
    }
  },
}
</script>
