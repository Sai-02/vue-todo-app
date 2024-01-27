<template>
    <div>
        <input type="checkbox" class="" @change="handleChange" :checked="listItem.isCompleted">
        {{ listItem.name }}
        <button @click="handleClickDelete">Remove</button>
    </div>
</template>

<script>
export default {
    name: "ListItem",
    props: ["listItem", "removeTask"],

    data: () => {
        return {
        }
    },
    methods: {
        handleClickDelete() {
            this.$props.removeTask(this.$props.listItem.id)
        },
        handleChange() {
            this.$props.listItem.isCompleted = !this.$props.listItem.isCompleted
        }
    },

    watch: {

    }
}
</script>




<style scoped></style>