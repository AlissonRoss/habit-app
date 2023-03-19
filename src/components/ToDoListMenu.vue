<script>
    export default {
        name: "ToDoListMenu",
        methods: {
        // send click information to parent
            closeToDoListMenu () {
                if (!this.mouseInMenu) {
                    this.$emit("closeToDoListMenu")
                }
            }
        }
    }
</script>
<template>
    <div id="add-task-menu">
        <div id="background" v-on:click=(closeToDoListMenu)>
            <div id="menu" @mouseover="mouseInMenu=true" @mouseleave="mouseInMenu=false">
                <h1 id="header-form">To Do List</h1>
                <input type="text" id="newInput" placeholder="Enter new task here">
                <button>Add</button>
                <form id="form">
                    <input type="checkbox" id="task-1">
                        <label for="task-1"> Task #1 </label><br>
                    <input type="checkbox" id="task-2">
                        <label for="task-2"> Task #2 </label><br>        
                    <input type="checkbox" id="task-3">
                    <label for="task-3"> Task #3 </label><br>
                </form>
            </div>
        </div>
    </div>
</template>
<style>
/* background becomes unclickable and a translucent grey cover */
#background {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    z-index: 1;
    display: flex;
    justify-content: center;
    align-items: center;
}
/* menu is a white box with a border */
#menu {
    width: 500px;
    height: 300px;
    background-color: white;
    border: 1px solid black;
    z-index: 2;
    text-align: center;
    border-radius: 25px;
}
#header-form{
    width: 50;
    padding-top: 1em;
    padding-bottom: 1em;
}
#form{
    text-align: left;
    padding-left: 8em;
    padding-top: 1em;
}
</style>