<template>
  <todo-list>
    <span slot="title" slot-scope="{ tasks }">
      To Do Tasks: {{ tasks.length }}
    </span>
  </todo-list>
</template>

<script>
import TodoList from '~/components/listing/todo/TodoList.vue'
export default {
  components: {
    TodoList,
  },
}
</script>
