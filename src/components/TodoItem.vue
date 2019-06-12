<template>
    <div id="item">
        <input :checked="todo.status" type="checkbox" @click="$emit('checkTodo')">
        <span :class="{ checked: todo.status }">
            {{numberList}}. {{todo.name}}
        </span>
        <button :disabled="todo.status" @click="$emit('editTodo')">Edit Todo</button>
        <button @click="$emit('removeTodo')">Hapus Todo</button>
    </div>
</template>

<script>
export default {
    name:'TodoItem',
    props:{
        todo: Object,
        index: Number,        
    },
    computed: {
        numberList:function(){
            return this.index+1
        }
    },
}
</script>