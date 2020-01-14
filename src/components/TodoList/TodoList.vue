<template>
    <div>
        <ul>
            <TodoListItem 
                v-for="(todo, i) of todos"
                v-bind:key="todo.id"
                v-bind:index="i"
                v-bind:todo="todo"
                v-on:remove-todo="removeTodo"
            />
        </ul>
    </div>
</template>

<script>
import TodoListItem from '@/components/TodoListItem/TodoListItem.vue'
export default {
    props: ['todos'],
    components: {
        TodoListItem
    },
    methods: {
        removeTodo(id) {
            this.$emit('remove-todo', id)
        }
    }
}
</script>

<style scoped>
    ul {
        list-style: none;
        margin: 0;
        padding: 0;
    }
</style>