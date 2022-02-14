<template>
  <div class="task-single grid">
      <h3>{{task.name}}</h3>
      <h3>{{task.type}}</h3>
      <div class="team-images">
          <div class="team-img-wrap grid">
              <img class="team-img" @mouseenter="showName(member.name)" @mouseleave="showName('')" :src="require(`../../images/${member.icon}`)" alt="" v-for="member in task.team" :key="member.id">
              <span class="img-overlay" v-if="(task.team.length-2>0)"  @mouseenter="showHiddenNames" @mouseleave="showName('')">+{{task.team.length-2}} </span>
              <div class="member-name">
                  <p>{{this.teammate}}</p>
              </div>
          </div>
      </div>
      <h3>{{task.start}}</h3>
      <h3>{{task.end}}</h3>
      
      <div class="progress-bar-con">
          <ProgressBar :percentage="task.progress" />
      </div>
  </div>
</template>

<script>
import ProgressBar from './ProgressBar'

export default {
    name: 'Task',
    props: {
        task: Object,
    },
    components: {
        ProgressBar
    },
    data() {
        return {
            teammate: ''
        }
    },
    methods: {
        showName(name) {
            this.teammate = name
        },
        showHiddenNames() {
            const nameArray = [];
            const count = 0;
            this.task.team.forEach(el => {
                if (count > 1) {
                    nameArray.push(el.name);
                }
                count = count + 1;
            });
            this.teammate = nameArray;
        }
    }
}
</script>

<style scoped>
    
</style>