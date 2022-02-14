<template>
    <div class="task-con flex">
        <div class="task-con-inner flex">
            <div class="task-con-head flex">
                <h2>Task Summary</h2>
                <button class="new-task-btn flex" @click="$emit('add-new-project', newProject)">
                    <img src="../../images/plus-regular-blue.png" alt="">
                    <p>New Task</p>
                </button>
            </div>
            <div class="sort-buttons">
                <button class="sort-btn" @click="ongoingClick" :style="ongoing? 'border-bottom: 3px solid blue;': 'border-bottom: none;'">Ongoing</button>
                <button class="sort-btn" @click="backlogClick" :style="backlog? 'border-bottom: 3px solid blue;': 'border-bottom: none;'">Backlog</button>
                <button class="sort-btn" @click="completedClick" :style="compOnly? 'border-bottom: 3px solid blue;': 'border-bottom: none;'">Completed</button>
            </div>
            <ul class="task-title-list grid">
                <li>Task Name</li>
                <li>Type</li>
                <li>Team</li>
                <li>Start</li>
                <li>End</li>
                <li>Progress</li>
            </ul>
            <div class="task flex" :key="task.id" v-for="task in tasks">
                <Task :task="task" v-if="this.compOnly && task.progress == 100"/>
                <Task :task="task" v-if="this.ongoing && task.progress != 100"/>
            </div>
            <h2 class="noTask" v-if="tasks.length<=0">No tasks</h2>
        </div>
    </div>
    
</template>

<script>
import Task from './Task'

export default {
    name: 'Tasks',
    props: {
        tasks: Array,
    },
    components: {
        Task
    },
    data() {
        return {
            compOnly: false,
            ongoing: true,
            backlog: false,
        }
    },
    methods: {
        ongoingClick() {
            this.compOnly = false
            this.ongoing = true
            this.backlog = false
        },
        completedClick() {
            this.compOnly = true
            this.ongoing = false
            this.backlog = false
        },
        backlogClick() {
            this.compOnly = false
            this.ongoing = false
            this.backlog = true
        },
    }
}
</script>

<style scoped>
   
</style>