<template>
    <ul>
        <TodoListItem v-for="todoItem in provideData.todoList" :key="todoItem.id" :item="todoItem"/>
    </ul>
</template>

<script>
import TodoListItem from "@/components/TodoListItem.vue"

export default {

    inject: ["provideData"],

    components: {
        TodoListItem
    }
}
</script>