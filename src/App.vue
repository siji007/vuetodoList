<template>
    <div id="app">
        <Header/>
        <AddTodo/>
        <Todos v-bind:todos="todos" 
        v-on:del-todo="deleteTodo" />
    </div>
</template>

<script>
import AddTodo from './components/layout/AddTodo';
import Header from './components/layout/Header';
import Todos from './components/Todos';
export default {
    name: 'app',
    components: {
        Header,
        Todos,
        AddTodo
    },

    data() {
        return {
            todos: [{
                    id: 1,
                    title: "Todo One",
                    completed: false
                },
                {
                    id: 2,
                    title: "Todo Two",
                    completed: false
                },
                {
                    id: 1,
                    title: "Todo Three",
                    completed: false
                },
            ]

        }

    },
    methods: {
        deleteTodo(id){
            this.todos = this.todos.filter(todo =>{
                todo.id !==id;
            });
        }
    },

}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
