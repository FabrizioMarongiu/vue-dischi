<template>
  <section class="card">
    <img :src="element.poster" alt="element.year" />
    <h2 class="white text-c">{{ element.title }}</h2>
    <h3 class="grey text-c">{{ element.author }}</h3>
    <h4 class="grey text-c">{{ element.genre }}</h4>
    <h4 class="white text-c">{{ element.year }}</h4>
  </section>
</template>

<script>
export default {
  name: "Cards",
  props: ["element"],
};
</script>

<style scoped lang="scss">
@import "../styles/vars";

.white {
  color: $white;
}
.grey {
  color: $grey;
}
.text-c {
  text-align: center;
}

.card {
  //   flex-basis: calc(100% / 8 - 20px);
  //   height: 270px;
  //   margin: 10px;
  background-color: #2e3a46;
  display: flex;
  flex-direction: column;
  align-items: center;
}
img {
  width: 100px;
  height: 100px;
  margin: 15px;
}
h2 {
  text-transform: uppercase;
}
</style>