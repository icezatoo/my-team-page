<template>
  <div class="app-main">
    <div class="header">
      <h2>The creative crew</h2>
      <div>
        <h5>WHO WE ARE</h5>
        <p>
          we are team of creatively diverse. driven. innovative individuals
          working in various locations from the world
        </p>
      </div>
    </div>
    <div class="content">
      <Card v-for="(item, index) in peoples" :key="index" :people="item"></Card>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Card from "./components/Card.vue";
import { People } from "./model/people";
@Component({
  components: {
    Card
  }
})
export default class App extends Vue {
  public peoples: People[] = [
    {
      linkImage: require("./assets/photo1.png"),
      name: "Bill mahoney",
      role: "product owner"
    },
    {
      linkImage: require("./assets/photo2.png"),
      name: "Saba Cabrera",
      role: "art director"
    },
    {
      linkImage: require("./assets/photo3.png"),
      name: "Shae Le",
      role: "teacher"
    },
    {
      linkImage: require("./assets/photo4.png"),
      name: "Skylah Lu",
      role: "ux designer"
    },
    {
      linkImage: require("./assets/photo5.png"),
      name: "Griff Richards",
      role: "devloper"
    },
    {
      linkImage: require("./assets/photo6.png"),
      name: "Stan john",
      role: "devloper"
    }
  ];
}
</script>

<style lang="scss">
html,
body {
  width: 100%;
  margin: 0;
  padding: 0;
  min-height: 100vh;
  font-size: 14px;
  font-family: "Poppins", sans-serif;
}

.app-main {
  padding: 10px;
}

.header {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(20rem, 1fr));
  width: 100%;
  grid-template-rows: 1fr;
  place-content: center;
  font-family: "PT Serif", serif;
}

.content {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  grid-template-rows: 1fr;
  width: 100%;
  grid-gap: 10px 10px;
  margin-top: 10px;
}

.content > * {
  align-self: start;
}
</style>
