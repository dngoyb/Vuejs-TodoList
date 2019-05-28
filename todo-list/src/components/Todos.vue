<template>
    <div>
        <div v-for="todo in todos" :key="todo.id">
            <TodoItem :todo="todo" @del-todo="$emit('del-todos', todo.id)"></TodoItem>
        </div>
    </div>
</template>

<script>
import TodoItem from './TodoItem'
export default {
    name: 'Todos',
    props: ['todos'],
    components: {
        TodoItem
    }
}
</script>