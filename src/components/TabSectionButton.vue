<template>
    <button class="tab-button" :style="`background-color:${color};`">
        <img :src="require(`../../images/${image}`)" alt="">
        <h3 :style="`color:${textColor}`">{{text}}</h3>
    </button>
</template>

<script>
export default {
    name:'TabSectionButton',
    props: {
        text: String,
        image: String,
        color: String,
        textColor: String,
    }
}
</script>

<style scoped>
   
</style>