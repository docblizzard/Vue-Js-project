<template>
    <div v-for="task in tasks" :key="task.id">
        <h3> {{ task.text }}</h3>
    </div>
</template>

<script>
export default {
    name:'Tasks-component',
    props: {
        tasks: Array
    }
}
</script>

<style lang="scss" scoped>

</style>