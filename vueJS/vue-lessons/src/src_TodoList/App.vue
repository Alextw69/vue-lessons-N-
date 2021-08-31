<script>
import TodoInput from './TodoInput'
import TodoItem from './TodoItem'

export default {
    components: {
        TodoInput,
        TodoItem,
    },
    data(){
        return {
            tasks: [],
        };
    },
    methods: {
        addTask(item){
            this.tasks.push(item);
        },
        removeTask(index){
            this.tasks.splice(index,1);
        },
    },
}
</script>
<template>
    <div>
        <todo-input @abc="addTask"></todo-input>
            <!--
                下層組件(todo-input) 發出自訂事件，
                上層組件(todo-list) 用『v-on:自訂事件』或『@自訂事件』接收
            -->

        <ol>
            <!-- <todo-item v-for="task in tasks" v-bind:xyz="task"/> -->
            <todo-item v-for="(task,index) in tasks"    
                       v-bind:xyz="task" 
                       @click.native="removeTask(index)" />
                <!--
                    上層組件(todo-list) 發出自訂屬性 (『v-bind:自訂屬性』或『：自訂屬性』)
                    下層組件(todo-item) 用props接收
                     @click.native 原生事件, index來自 v-for="(task,index) in tasks"
                    *** 在組件上 <todo-item> 使用click事件 所以要加上原生事件 ***
                -->
        </ol>
    </div>
</template>
