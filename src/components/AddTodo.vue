<template>
    <div>
        <form @submit="addTodo">
            <input type="text" v-model="title" name="title" placeholder="Add to list...">
            <p><input type="submit" value="Add" class="btn"> </p>
        </form>
    </div>
</template>

<script>
import uuid from 'uuid';

export default {
    name: "AddTodo",
    data() {
        return{
            title: ''
        }
    },
    methods: {
        addTodo(e) {
            e.preventDefault();
            const newTodo = {
                id: uuid.v4(),
                title: this.title,
                completed: false
            }
            this.$emit('add-todo', newTodo);
        }
    }
}
</script>

<style scoped>
    .btn{
        color: white;
        background: hsl(195, 53%, 79%);
        border: 0px;
        width: 60%;
        padding: 10px;
        border-radius: 10px;
        cursor: pointer;
    }
    .btn:hover{
        background: hsl(195, 53%, 82%);
    }
    .btn:active{
        background: hsl(195, 53%, 76%);
    }
    .btn:focus {
        outline: 0;
    }
    input{
        font-family: 'Montserrat';
    }
    input[type=text], select {
        width: 60%;
        padding: 12px 20px;
        margin: 8px 0;
        display: inline-block;
        border: 1px solid lightblue;
        border-radius: 0px;
        background: hsla(0, 0%, 100%, 0.5);
        box-sizing: border-box;
        outline-color: white;
        color: black;
        border-radius: 10px;
    }
</style>


