<script>
export default {
    name: "ToDoButton",
    methods: {
        // send click information to parent
        openToDoListMenu() {
            this.$emit("openToDoListMenu")      
        }
    }
}
</script>
<template>
    <div id="toDoButton">
        <button v-on:click=(openToDoListMenu)>To-Do List</button>   
    </div>
</template>