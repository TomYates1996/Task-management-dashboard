<template>
  <div class="prog-bar-con flex">
      <div class="prog-bar-frame">
          <div class="prog-bar-fill" :style="`width:${percentage}%;`"></div>
      </div>
      <h5>{{percentage}}%</h5>
  </div>
</template>

<script>
export default {
    name: 'ProgressBar',
    props: {
        percentage: Number,
    }
}
</script>

<style scoped>
    
</style>