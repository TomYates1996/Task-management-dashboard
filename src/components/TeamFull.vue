<template>
    <div class="main-con flex">
        <button class="close" @click="$emit('closeTeam', team)">
            X
        </button>
        <div class="team-member" v-for="member in team" :key="member.id">
            <h3>{{member.name}}</h3>
            <img :src="require(`../../images/${member.icon}`)" alt="">
            <button class="remove-btn" @click="removeMember(member)">Remove from team</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'TeamFull',
    props: {
        team: Array,
    },
    methods: {
        removeMember(member) {
            this.$emit('member-gone', member)
        }
    }

}
</script>

<style>
    
</style>