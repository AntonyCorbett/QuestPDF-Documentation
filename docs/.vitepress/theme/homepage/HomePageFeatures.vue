<template>
  <div class="container">

    <h2>Designed to be efficient</h2>

    <div class="features">

      <section class="feature" v-for="feature of FeaturesContent" :key="feature.title">
        <img class="icon" :src="feature.icon" alt="" />
        <h3 class="title">{{ feature.title }}</h3>
        <p class="description">{{ feature.description }}</p>
      </section>

    </div>
  </div>
</template>

<script setup>

import { FeaturesContent } from './configuration';

</script>

<style scoped>

.features {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-gap: 96px;

  margin-top: 64px;
}

@media screen and (max-width: 700px) {
  .features {
    grid-template-columns: 1fr;
  }
}

.feature {
  display: grid;
  grid-template-areas:
      "icon title"
      "icon description";
  grid-template-columns: auto 1fr;
  grid-template-rows: auto 1fr;
  grid-gap: 8px 24px;
}

@media screen and (max-width: 1000px) {
  .feature {
    grid-template-areas:
      "icon"
      "title"
      "description";
    grid-template-columns: auto;
    grid-template-rows: auto auto auto;
    grid-gap: 12px 0;
  }
}

.feature img.icon {
  grid-area: icon;

  justify-self: start;
  align-self: start;
  height: 48px;
  width: 48px;
}

.feature h3.title {
  grid-area: title;

  margin: 0;
}

.feature p.description {
  grid-area: description;

  justify-self: start;
  align-self: start;
}

</style>