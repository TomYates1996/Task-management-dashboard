<template>
  <div class="main flex">
    <TabSection @tab-change="changeTab" :sel="this.sel"/>
    <NewProject v-if="addNewProject" @create-project="createProject" @close-form="closeForm"/>
    <Dashboard :email="email" @add-new-project="showNewProject" :tasks="this.tasks"/>
  </div>
  
</template>

<script>
import Dashboard from './Dashboard'
import NewProject from './NewProject'
import TabSection from './TabSection'

export default {
    name: 'MyTaskApp',
    components: {
      Dashboard,
      NewProject,
      TabSection,
    },
    props: {
        email: String,
        password: String,
    },
    data() {
      return {
        addNewProject: false,
        tasks: [
                // {name:"Call mr smith", type: "Comms", team: "Bob and Joel", start:"Starting Date", end:"Ending Date", progress:"progress", completed:true},
                // {name:"Spin Car", type: "Random", team: "Phil and Mark", start:"Starting Date", end:"Ending Date", progress:"progress", completed:false},
                // {name:"Email John", type: "Comms", team: "Pete and Beo", start:"Starting Date", end:"Ending Date", progress:"progress", completed:false},
            ],
            sel: 1,
      }
    },
    methods: {
      showNewProject() {
        this.addNewProject = !this.addNewProject
      },
      createProject(projectDetails) {
          this.tasks = [...this.tasks, projectDetails]
          this.addNewProject = false
      },
      closeForm() {
        this.addNewProject = false
      },
      changeTab(n) {
        this.sel = n;
        if (this.sel == 6) {
          this.$emit('sign-out');
        }
      }
    }
}
</script>

<style scoped>
</style>