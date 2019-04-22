<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <div class="item">
            <span class="checkbox"><input type="checkbox" v-on:change="markComplete"></span>
            {{todo.title}}
        </div>
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
        border: #add8e6;
        background: hsla(195, 53%, 79%, 0.5);
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
        background: hsl(350, 100%, 88%);
        border: none;
        padding: 10px 20px;
        border-radius: 10px;
        cursor: pointer;
    }
    .del:hover{
        background: hsl(350, 100%, 91%);
    }
    .del:active{
        background: hsl(350, 100%, 85%);
    }
    .del:focus {
        outline: 0;
    }
    input[type="checkbox"]{
        position: relative;
        display: block;
        opacity: 1;
        cursor: pointer;
        border: 0px;
        width: 20px;
        height: 20px;

    }
    input[type="checkbox"]:checked {

        box-shadow: 0 0 0 2px pink;
    }
    .item{
        padding: 10px;
    }
</style>
