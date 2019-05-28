<template>
    <div>
        <div v-for="todo in todos" :key="todo.id">
            <TodoItem :todo="todo"></TodoItem>
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