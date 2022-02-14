<template>
    <div class="page flex">
        <div class="page-cover"></div>
        <form  @submit="onSubmit" class="form-new-proj">
            
            <p class="close-form" @click="closeForm">x</p>
            <h3>Create New Project</h3>
            <div class="form-control-new flex">
                <label>Name</label>
                <input type="text" v-model="name" name="name" placeholder="Project name" required>
            </div>
            <div class="form-control-new flex">
                <label>Team</label>
                <input type="text" v-model="search" name="search" placeholder="Search by name or email">
            </div>
            <div class="user-box">
                <div v-for="user in filteredUsers" :key="user.id">
                    <User :user="user" @add-team="addTeam"/>
                </div>
                <div class="empty-text" v-if="this.allUsers.length <= 0 || filteredUsers.length < 1">
                    <h3>No staff found</h3>
                </div>
                <!-- <div v-for="i in 4" :key="i">
                    <User :user="filteredUsers[i]" @add-team="addTeam"/>
                </div> -->
            </div>

            <div class="team-section flex">
                <h3>Current Team</h3>
                <SelectedTeam :team="this.teamExpanded? this.team : this.shortTeam" :teamLength="this.team.length" 
                :full="this.teamExpanded" @expand-team="teamShow" @remove-member="removeTeam"/>               
            </div>

            <div class="project-type-con flex">
                <h2>Project type</h2>
                <select class="project-type" @change="changeProjectType($event)" required>
                    <option value="" selected disabled>Choose type</option>
                    <option v-for="type in projectTypes" :value="type.id" :key="type.id">{{ type.name }}</option>
                </select>
            </div>
            
            
            <div class="date-boxes flex">
                <input type="text" v-model="start" placeholder="Start date" onfocus="(this.type='date')" required >
                <input type="text" v-model="end" placeholder="End date" onfocus="(this.type='date')" required>
            </div>
            <!-- <button class="create-btn">Create Project</button> -->
            <input type="submit" value="Create Project" class="create-btn">
      </form>
  </div>
</template>

<script>
import User from './User'
import ButtonTeam from './ButtonTeam'
import TeamFull from './TeamFull'
import SelectedTeam from './SelectedTeam'

export default {
    name: 'NewProject',
    components: {
        User,
        ButtonTeam,
        TeamFull,
        SelectedTeam,
    },
    data() {
        return {
            teamExpanded: false,
            maxTeam: 6,
            team: [],
            name: '',
            start: '',
            end: '',
            search: '',
            allUsers: [
            {
            name: 'Bob',
            email: 'bob@mytask.com',
            icon: 'man2big.png'
            },
            {
            name: 'Philip',
            email: 'phil@mytask.com',
            icon: 'man2big.png'
            },
            {
            name: 'Greg',
            email: 'Greg@mytask.com',
            icon: 'man1big.png'
            },
            {
            name: 'Kevin',
            email: 'Kev@mytask.com',
            icon: 'man2big.png'
            },
            {
            name: 'Nigel',
            email: 'nigell@mytask.com',
            icon: 'man2big.png'
            },
            {
            name: 'Fred',
            email: 'fred@mytask.com',
            icon: 'man1big.png'
            },
            {
            name: 'Betty',
            email: 'betty@mytask.com',
            icon: 'woman1big.png'
            },
            {
            name: 'Mike',
            email: 'mike@mytask.com',
            icon: 'man1big.png'
            },
            {
            name: 'Peter',
            email: 'peter@emailio.com',
            icon: 'man1big.png'
            },
            ],
            projectTypes: [
                { name: "Comms", id: 1 },
                { name: "Email", id: 2 },
                { name: "Test4", id: 3 },
                { name: "Other", id: 4 }
            ],
            selectedProjectType: null,
            shortTeam: [],
        }
    },
    computed: {
        filteredUsers() {
            return this.allUsers.filter(user => user.name.toLowerCase().includes(this.search.toLowerCase()) || user.email.toLowerCase().includes(this.search.toLowerCase()))
        }
    },
    methods: {
        addTeam(user){
            this.allUsers.splice(this.allUsers.indexOf(user), 1)
            this.team = [...this.team, user]
            if (this.team.length < 6){
                this.shortTeam = this.team
            }     
        },
        removeTeam(member) {
            this.team.splice(this.team.indexOf(member), 1)
            this.allUsers = [...this.allUsers, member]
            if (this.team.length < 6) {
                this.shortTeam = this.team
                this.teamExpanded = false
            }
        },
        teamShow() {
            this.teamExpanded = !this.teamExpanded;
        },
        changeProjectType (event) {
            this.type = event.target.options[event.target.options.selectedIndex].text
        },
        onSubmit(e) {
            e.preventDefault()
            const projectDetails = {
                name: this.name,
                type: this.type,
                team: this.team,
                start: this.start,
                end: this.end,
                progress: 25
            }
            this.$emit('create-project', projectDetails)
            this.name = '',
            this.type = '',
            this.team = '',
            this.start = '',
            this.end = '',
            this.progress = ''
        },
        closeForm() {
            this.$emit('close-form')
        }
    }
    }


</script>

<style scoped>
   
</style>