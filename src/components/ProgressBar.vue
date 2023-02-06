<template>
  <div class="progress-bar">
    <div class="progress-bar__text">{{ progressValue }} %</div>
    <div class="progress-bar__bar" :style="{ 'width': widthProgress === 0 ? '5px' : `${widthProgress}px`, 'background-color': progressColor }"></div>
  </div>
</template>

<script>
export default {
  name: "ProgressBar",
  props: ["progressValue", "widthProgress", "progressColor"],

}
</script>

<style scoped>
.progress-bar {
  display: flex;
  flex-direction: row;
  align-items: center;
  padding: 18px 0;
  margin-bottom: 50px;
}

.progress-bar__text {
  color: var(--white-color);
}
.progress-bar__bar {
    height: 10px;
    margin-left: 20px;
    color: var(--white-color);
}
</style>