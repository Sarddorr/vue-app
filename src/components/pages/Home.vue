<template lang="html">
  <div class="home-container">
    <div class="home-cards">
      <CardBlock />
      <SiteSpeed />
    </div>
    <div class="home-cards">
      <UserBarCharts />
    </div>
  </div>
</template>

<script setup>
import CardBlock from "../cards/CardBlock.vue";
import SiteSpeed from "../cards/SiteSpeed.vue";
import UserBarCharts from "../charts/UserBarCharts.vue";
</script>

<style scoped lang="scss">
.home {
  &-container {
    position: absolute;
    top: 70px;
    left: 300px;
    width: calc(100% - 300px);
    height: calc(100vh - 70px);
    display: flex;
    flex-direction: column;
    box-sizing: border-box;
    padding: 20px;
    overflow-y: auto;
  }

  &-cards {
    display: flex;
    gap: 20px;
    width: 100%;

    & > div {
      max-width: 100%;
      width: 100%;
      height: 100%;
    }
  }
}
@media (max-width: 1440px) {
  .home {
    &-container {
      left: 200px;
      width: calc(100% - 200px);
    }
  }
}

@media (max-width: 1280px) {
  .home-cards {
    flex-direction: column;
  }
}

@media (max-width: 1024px) {
  .home {
    &-container {
      left: 0;
      width: 100%;
    }
    &-cards {
      flex-direction: column;
    }
  }
}
</style>
