<template>
  <div class="progress-bar">
    <div class="progress-bar__text">{{ progress }} %</div>
    <div class="progress-bar__bar"></div>
  </div>
</template>

<script>
export default {
  name: "ProgressBar",
  props: ["initialValue", "value"],
  data() {
    return {
      progress: this.initialValue
    };
  }
}
</script>

<style scoped>
.progress-bar {
  display: flex;
  flex-direction: row;
}
.progress-bar__bar {
    width: 420px;
    height: 10px;
    background-color: #04AA6D;

    color: white;
}
</style>