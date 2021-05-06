<template>
  <header>
    <img src="@/assets/assets-vue-dischi/logo.png" alt="" />
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped lang="scss">
header {
  width: 100%;
  height: 50px;
  background-color: #2e3a46;
  display: flex;
  align-items: center;
}
img {
  width: 40px;
}
</style>