<template>
    <div class="user-con flex">
        <img :src="require(`../../images/${user.icon}`)" alt="">
        <div class="text-layer flex">
            <h4>{{user.name}}</h4>
            <p>{{user.email}}</p>
        </div>
        <!-- <p>{{onTeam}}</p> -->
        
        <button class="cover-btn" @click="$emit('add-team', user)"></button>
    </div>
</template>

<script>
export default {
    name: 'User',
    props: {
        user: Object,
        onTeam: {type: Boolean, default: false}
    },
}
</script>

<style scoped>

    
</style>