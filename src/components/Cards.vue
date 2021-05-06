<template>
  <section class="card">
    <img
      src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg"
      alt=""
    />
    <h2 class="white">new jersey</h2>
    <h3 class="grey">Bon Jovy</h3>
    <h4 class="grey">1988</h4>
    <h4 class="white">rock</h4>
  </section>
</template>

<script>
export default {
  name: "Cards",
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

.card {
  flex-basis: calc(100% / 8 - 20px);
  height: 270px;
  background-color: #2e3a46;
  margin: 10px;
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
  text-align: center;
}
</style>