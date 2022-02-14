<template>
    <div class="notify-con flex">
        <img :src="require(`../../images/${photo}`)" alt="">
        <p><strong>{{who}}</strong> {{didWhat}} <strong>{{project}}</strong> </p>
        <button class="more-info-btn">
            <img src="../../images/ellipsis-regular.png" alt="">
        </button>
    </div>
</template>

<script>
export default {
    name: 'NotificationBox',
    props: {
        project: String,
        who: String,
        photo: String,
        didWhat: String,
    }
}
</script>

<style scoped>
    
</style>