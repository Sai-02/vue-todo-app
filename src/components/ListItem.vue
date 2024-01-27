<template>
    <div>
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
        }
    }
}
</script>

<style scoped></style>