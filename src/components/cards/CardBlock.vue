<template>
  <div class="statistics">
    <div class="statistics-container">
      <div class="statistics-items">
        <div class="statistics-item" v-for="item in 6">
          <div class="statistics-header">
            <h2 class="statistics-header-title">Pages</h2>
            <p>...</p>
          </div>
          <div class="statistics-content">
            100
          </div>
          <div class="statistics-events">
            <button class="statistics-event add">+</button>
            <button class="statistics-event view">View all</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {

}
</script>

<style lang="scss" scoped>
.statistics {
  width: 100%;
  max-width: 100%;

  &-items {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    row-gap: 12px;
  }

  &-item {
    max-width: calc(100% / 3 - 12px);
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    background: #3B82F6;
    border-radius: .4rem;
  }

  &-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    padding: 1.2rem;

    &-title {
      font-size: 1.2rem;
      line-height: 1.2rem;
      font-weight: 500;
      color: white;
    }

    & p {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 1rem;
      height: .5rem;
      color: white;
    }
  }

  &-content {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 3.2rem;
    line-height: 130%;
    font-weight: 600;
    color: white;
    padding: 1rem 0;
  }

  &-events {
    display: flex;
    align-items: center;
    justify-content: center;
    column-gap: .6rem;
    width: 100%;
    padding: 1.2rem;
  }

  &-event {
    background: unset;
    border: unset;

    &.add {
      background: white;
      color: #0a65f7;
      font-size: 1.8rem;
      line-height: 1.8rem;
      width: 2rem;
      height: 2rem;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 50%;
    }

    &.view {
      text-align: center;
      color: #0a65f7;
      border-radius: .4rem;
      background: white;
      padding: .5rem 1.5rem;
    }
  }
}
@media (max-width: 1024px) {
  .statistics{
    &-items{
      row-gap: .3rem;
    }
    &-item{
      max-width: calc(100%/3 - 3px);
    }
  }
}
@media (max-width: 500px) {
  .statistics{
    &-item{
      max-width: calc(100%/2 - 2px);
    }
  }
}
</style>