<template>
<div>
    <input 
    class="new-todo"
    @key-up.enter="addTask"
    placeholder="O que precisa ser feito ?"
    >
</div>
</template>

<script>
import { Task } from '../models/task'

export default {
    data () {
        return {           
        }
    },
    methods: {
        addTask($event) {
            let value = $event.target.value
            let task = new Task ()
            task.completed = false
            task.title = value
            this.$emit('newTask', task)
            $event.target.value = ''
        }
    }
}
</script>

<style>
.todoapp input::-webkit-input-placeholder {
    font-style: italic;
    font-weight: 300;
    color: #E6E6E6;
}

.todoapp input::-moz-input-placeholder {
    font-style: italic;
    font-weight: 300;
    color: #E6E6E6;
}

.todoapp input::input-placeholder {
    font-style: italic;
    font-weight: 300;
    color: #E6E6E6;
}

.new-todo,
.edit {
    position: relative;
    margin: 0;
    width: 100%;
    font-size: 24px;
    font-family: inherit;
    font-weight: inherit;
    line-height: 1.4em;
    border: 0;
    color: inherit;
    padding: 6px;
    border: 1px solid #999;
    box-shadow: inset 0 -1px 5px 0 rgba(0, 0, 0, 0.2);
    box-sizing: border-box;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing:grayscale;       
}

.new-todo {
    padding: 16px 16px 16px 60px;
    border: none;
    background: rgba(0, 0, 0, 0.03);
    box-shadow: inset 0 -2px -1px rgba(0, 0, 0, 0.03);
}

</style>