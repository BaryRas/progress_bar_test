<template>
  <div class="home">
    <div class="header">
      <h3>Test technique WEB-ATRIO réalisé par RASOLOMANANA Bary réalisé le 06/02/2023</h3>
    </div>
    <section>
      <div class="container">
        <div  v-for="(data, index) in dataInit" :key="index">
          <h4 class="sub-header-text">{{ data.title }}</h4>
          <progress-bar 
            :progressValue="progressValue == null ? data.initValue : progressValue" 
            :progressColor="colorProgress(progressValue == null ? data.initValue : progressValue)" 
            :widthProgress="widthProgress(progressValue == null ? data.initValue : progressValue)" />
        </div>
        
      </div>
      <div class="controller">
        <button @click="initValues()">Remettre à zero les compteurs</button>
        <button @click="incrementValue(5)">Ajouter 5%</button>
        <button @click="incrementValue(10)">Ajouter 10%</button>
      </div>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
import ProgressBar from "@/components/ProgressBar.vue"

export default {
  name: "HomeView",
  components: {
    ProgressBar
  },
  data() {
    return {
      progressValue: null,
      progressbar: null,
      dataInit: [
        { title: "Initialisation du test technique", initValue: 50 },
        { title: "Avancement de la phase de développement", initValue: 25 },
      ]
    }
  },
  methods: {
    colorProgress(color) {
      if (color <= 25) {
        return  "#7160E8"
      } else if (color > 25 && color <= 50) {
        return  "#60ADE8"
      } else if (color > 50 && color <= 75) {
        return  "#60E8B6"
      } else if (color > 75 && color <= 100) {
        return  "#30DB63"
      }
    },

    widthProgress(val) {
      return val * 10
    },

    initValues() {
      this.progressValue = 0;
      this.progressbar = 0.5;
    },

    incrementValue(val) {
      if (this.progressValue < 0 || this.progressValue >= 100) {
        return;
      } else {
        this.progressValue += val;
      }
       
    },
  }
};
</script>

<style>
/* Layout Properties */
.home {
  height: 100vh;
  background: var(--dark-grey-color) 0% 0% no-repeat padding-box;
  opacity: 1;
}

.header {
 display: flex;
 justify-content: center;
 padding-top: 81px;
 margin-bottom: 100px;
}

section {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

h3 {
    width: 396px;
    height: 42px;
    font-family: "Roboto";
    font-weight: bold;
    font-size: 16px;
    letter-spacing: 0px;
    color: var(--white-color);
    opacity: 1;
}


.container {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  width: 898px;
  height: 158px;
}

.sub-header-text {
  font-family: "Roboto";
  font-size: 14px;
  letter-spacing: 0px;
  color: var(--white-color);
  opacity: 1;
}

.controller{
  margin-top: 100px;
}

button {
  text-decoration: none;
  padding: 10px 15px;
  font-family: inherit;
  background-color: var(--light-grey-color);
  border: 1px solid var(--light-grey-color);
  box-shadow: 0px 3px 6px #00000029;
  color: var(--white-color);
  cursor: pointer;
  margin-right: 0.5rem;
  display: inline-block;
}
</style>