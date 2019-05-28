<template>
        <div class="todo-items" v-bind:class="{'is-complete': todo.completed}">
            <p>
                <input type="checkbox" @change="markComplete">
                {{todo.title}}
                <button id="del" @click="$emit('del-todo', todo.id)">x</button>
            </p>
        </div>
       
</template>

<script>
export default {
    name: 'TodoItem',
    props: ['todo'],

    methods: {
        markComplete(){
            this.todo.completed = !this.todo.completed
        }
    },
}
</script>

<style scoped>
.is-complete {
    text-decoration: line-through;
}
.todo-items {
    background: whitesmoke;
    padding:  10px;
    border-bottom: 1px #ccc dotted
}

#del {
    color: red;
    float: right;
    cursor: pointer;
    text-transform: uppercase;
    font-weight: 800;
    border: none
}
</style>
