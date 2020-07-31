<template>
  <div class="card">
    <img class="image-people" :alt="people.name" :src="people.linkImage" />
    <span class="title-rule">{{ people.role }}</span>
    <span class="name-title">{{ people.name }}</span>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";
import { People } from "../model/people";
@Component
export default class Card extends Vue {
  @Prop() people!: People;
}
</script>

<style lang="scss" scoped>
.card {
  display: grid;
  grid-template-columns: auto 50px;
  grid-template-rows: auto 1fr;
  width: 100%;
  height: 100%;

  &:nth-child(2n) {
    margin-top: 58px;
  }
}

.name-title {
  font-weight: bold;
  font-size: 1.2rem;
  grid-column: 1/3;
}

.image-people {
  display: block;
  object-fit: cover;
  width: 100%;
}

.title-rule {
  writing-mode: vertical-rl;
  text-orientation: mixed;
  display: flex;
  align-items: center;
  font-size: 1.2rem;
}
</style>
