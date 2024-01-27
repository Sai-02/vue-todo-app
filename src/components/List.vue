<template>
    <div class="list-container">
        <h3 class="list-heading">Todo App</h3>
        <ul class="">
            <li class="" v-for="listItem in todoListArray" :key="listItem.id">
                <ListItem v-bind:listItem="listItem" :removeTask="removeTask" />
            </li>
        </ul>
        <button class="" @click="showAddTaskInput">Add Task</button>
        <div class="" v-show="shouldShowAddTaskInput">
            <input type="text" class="" v-model="inputValue"> <button @click="addTask">Add</button>
        </div>
    </div>
</template>

<script>

import ListItem from './ListItem.vue';

export default {
    name: "List",
    components: {
        ListItem
    },
    data: () => {
        return {
            todoListArray: [
                {
                    id: "3724y242he2r",
                    name: "Learn Vue",
                    isCompleted: false,
                }, {
                    id: "48y3h83h8h43r",
                    name: "Learn Python", isCompleted: false
                }
            ],
            shouldShowAddTaskInput: false,
            inputValue: ""
        };
    },
    methods: {
        getUniqueID() {
            return "id" + Math.random().toString(16).slice(2)
        },
        showAddTaskInput() {
            console.log("great");
            this.shouldShowAddTaskInput = true;
        },
        addTask() {
            this.todoListArray.push({
                id: this.getUniqueID(),
                name: this.inputValue,
                isCompleted: false
            });
            this.showAddTaskInput = false;
            console.log(this.inputValue);
        },
        removeTask(id) {
            this.todoListArray = this.todoListArray.filter((val) => val.id !== id)
        }

    },
    computed: {},
    watchers: {},
}
</script>

<style scoped>
.list-container {
    background: white;
    border-radius: 0.6rem;
    padding: 1rem;
    display: flex;
    flex-direction: column;
    gap: 1rem;
}

.list-heading {
    color: #3b3b71
}
</style>