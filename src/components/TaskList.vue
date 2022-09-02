<template>
    <ul class="todo-list">
        <li
        v-for="todo in sortedTasks"
        class="todo"
        >
        <div class="view">
            <input 
            type="checkbox" 
            class="toogle"
            @click="complete(todo)"
            >
            <label :class="{ 'todo-completed': todo.completed }">
            {{ todo.title }}
            </label>
        </div>
        </li>
    </ul>
</template>

<script>
    export default {
        props: ['todolist'],
        computed: {
            sortedTasks: function() {
                let sorted = this.todolist
                return sorted.sort(function (a,b){
                    if (a.title < b.title) return -1 
                    if (a.title > b.title) return 1
                    return 0
                })
            }
        },
        methods: {
            completedTask (task) {
                task.completed = !task.completed
            }
        }
    }
</script>

<style>
    .todo-list {
        margin: 0;
        padding: 0;
        list-style: none;
    }

    .todo-list li {
        position: relative;
        font-size: 24px;
        border-bottom: 1px solid #EDEDED;
    }

    .todo-completed {
        text-decoration: line-through;
    }

    .todo-list li:last-child {
        border-bottom: none;
    }

    .todo-list li.editing {
        border-bottom: none;
        padding: 0;
    }

    .todo-list li.editing .edit {
        display: block;
        width: 506;
        padding: 12px 16px;
        margin: 0 0 0 43px;
    }

    .todo-list li.editing .view {
        display: none;
    }

    .todo-list li .toogle {
        text-align: center;
        z-index: 99;
        width: 40px;
        height: auto;
        position: absolute;
        top: 0;
        bottom: 0;
        margin: auto 0;
        border: none;
        -webkit-appearance: none;
        appearance: none;
    }

    .todo-list li .toogle:after {
        content: url('../assets/circle.svg');
    }

    .todo-list li .toogle:checked:after {
        content: url('../assets/check_circle.svg');
    }

    .todo-list li label {
        word-break: break-all;
        padding: 15px 60px 15px 15px;
        margin-left: 45px;
        display: block;
        line-height: 1.2;
        transition: color 0.4s;
    }

    .todo-list li.completed label {
        color: #D9D9D9;
        text-decoration: line-through;
    }

    .todo-list li .destroy {
        display: none;
        position: absolute;
        top: 0;
        right: 10px;
        bottom: 0;
        width: 40px;
        height: 40px;
        margin: auto 0;
        font-size: 30px;
        color: #CC9A9A;
        margin-bottom: 11px;
        transition: color 0.2s ease-out;
    }

    .todo-list li .destroy:hover {
        color: #AF5B5E;
    } 

    .todo-list li .destroy:after {
        content: 'X';
    }

    .todo-list li:hover .destroy {
        display: block;
    }

    .todo-list li.editing:last-child {
        margin-bottom: -1px;
    }

    @media screen and (-webkit-min-device-pixel-ratio:0) {
        .toogle-all,
        .todo-list li .toogle {
            background: none;
        }

        .todo-list li .toogle {
            height: 40px;
        }

        .toogle-all {
            -webkit-transform: rotate(90deg);
            transform: rotate(90deg);
            -webkit-appearance: none;
            appearance: none;
        }
    }

</style>