<template>
  <TodoList>
    <span slot="title" slot-scope="{ tasks }">
      To Do tasks for :{{ tasks.length }}
    </span>
  </TodoList>
</template>

<script>
import TodoList from '~/components/listing/todo/TodoListSpare'
export default {
  components: { TodoList },
}
</script>
