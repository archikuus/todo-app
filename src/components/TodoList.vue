<template>
    <div>
        <p>Completed Tasks: {{ todos.filter(todo => {return todo.done === true}).length }}</p>
        <p>Pending Tasks: {{ todos.filter(todo => {return todo.done === false}).length }}</p>
        <todo v-on:delete-todo="deleteTodo" v-on:complete-todo="completeTodo" v-for="todo in todos" :todo.sync="todo"></todo>
    </div>
    
</template>

<script type="text-javascript">
import Todo from './Todo'

    export default {
        props: ['todos'],
        components: {
            Todo
        },
        methods: {
            deleteTodo (todo) {
                const todoIndex = this.todos.indexOf(todo)
                this.todos.splice(todoIndex, 1)
            }
        }

    }
</script>

<style>

</style>