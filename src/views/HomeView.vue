<template>
  <div class="home">
    <div class="header">
      <h3>Test technique WEB-ATRIO réalisé par RASOLOMANANA Bary réalisé le 06/02/2023</h3>
    </div>
    <section>
      <div class="container">
        <h3 class="sub-header-text">Initialisation du test technique</h3>
        <progress-bar :initialValue="50" />
        <h3 class="sub-header-text">Avancement de la phase de développement</h3>
        <progress-bar :initialValue="25" />
      </div>
      <div class="controller">
        <button >Remettre à zero les compteurs</button>
        <button>Ajouter 5%</button>
        <button>Ajouter 10%</button>
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
  }
};
</script>

<style lang="scss">
/* Layout Properties */
.home {
  top: 83px;
  left: 0px;
  width: 1429px;
  height: 612px;
  /* UI Properties */
  background: #242424 0% 0% no-repeat padding-box;
  background: #242424 0% 0% no-repeat padding-box;
  opacity: 1;
}

.header {
 display: flex;
 justify-content: center;
 padding-top: 81px;
}

h3 {
    width: 396px;
    height: 42px;
    font-family: "Roboto";
    font-weight: bold;
    font-size: 16px;
    letter-spacing: 0px;
    color: #FFFFFF;
    opacity: 1;
}

.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: left;
  margin-top: 100px;
  width: 898px;
  height: 158px;
}

.sub-header-text {
  font-family: "Roboto";
  font-size: 14px;
  letter-spacing: 0px;
  color: #FFFFFF;
  opacity: 1;
}

.controller{
  margin-top: 100px;
}

button {
  text-decoration: none;
  padding: 0.75rem 1.5rem;
  font: inherit;
  background-color: #373737;
  border: 1px solid #373737;
  box-shadow: 0px 3px 6px #00000029;
  color: white;
  cursor: pointer;
  margin-right: 0.5rem;
  display: inline-block;
}
</style>