<template>
    <div class="selected-team-con flex">
        <div class="team-wrap flex">
            <h4 v-if="this.team.length <= 0">No team-members selected</h4>
            <div class="team-member" v-for="member in team" :key="member.id">
                <img class="team-img-select" :src="require(`../../images/${member.icon}`)" alt="">
                <button class="remove-team-btn-in" @click="$emit('remove-member', member)">remove</button>
            </div>
            <button class="expand-btn" v-if="this.teamLength>5" @click="expandTeam">{{full? "hide":`+${teamLength-this.team.length}`}}</button>
        </div>        
    </div>
</template>

<script>
export default {
    name: 'SelectedTeam',
    props: {
        team: Array,
        full: Boolean,
        teamLength: Number,
    },
    methods: {
        expandTeam() {
            this.$emit('expand-team')
        }
    }
}
</script>

<style scoped>
  
</style>