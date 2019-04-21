<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete">
            {{todo.title}}
        </p>
        <p>
            <button @click="$emit('del-todo', todo.id)"
             class="del">Delete</button>
        </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete() {
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>
<style scoped>
    .todo-item{
        border: lightblue;
        background: rgb(220, 241, 248);
        border-width: 2px;
        border-style: solid;
        border-radius:10px;
        margin-top: 10px;
        width: 60%;
        margin-left: auto;
        margin-right:auto;

    }
    .is-complete{
        text-decoration: line-through;
    }
    .del{
        text-align: center;
        align-content: right;
        color: white;
        background: pink;
        border: none;
        padding: 10px 20px;
        border-radius: 10px;
    }
    input[type="checkbox"]:checked {
        box-shadow: 0 0 0 2px pink;

    }
</style>
