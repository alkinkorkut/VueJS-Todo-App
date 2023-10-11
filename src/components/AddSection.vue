<template>
    <label for="todoText"></label>
    <input v-model="todoText" @keydown.enter="addNewTodo(todoText)" type="text" id="todoText" placeholder="Write something">
</template>

<script>
export default {
    props: {
        addNewTodo: {
            type: Function,
            required: true
        }
    },
    data() {
        return {
            todoText: null
        };
    },
}
</script>