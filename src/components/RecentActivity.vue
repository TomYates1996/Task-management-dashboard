<template>
    <div class="wrapper flex">
        <h2>{{amount}} Tasks</h2>
        <p>{{text}}</p>
        <div class="graph" :style="`background-color:${color};`"></div>
    </div>
</template>

<script>
export default {
    name: 'RecentActivity',
    props: {
        amount: Number,
        text: String,
        color: String,
    }

}
</script>

<style scoped>
    
</style>