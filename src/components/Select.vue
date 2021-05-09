<template>
  <div class="select">
    <label for="gender">Scegli un genere musicale</label>
    <select
      name="gender"
      id="genere"
      v-model="choice"
      @change="$emit('send', choice)"
    >
      <option value="all">All</option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option>
    </select>
  </div>
</template>

<script>
export default {
  name: "Select",
  data() {
    return {
      choice: "All",
    };
  },
};
</script>

<style scoped lang="scss">
.select {
  height: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
}

select {
  margin: 0 20px;
  width: 100px;
  height: 30px;
  background-color: #095ba8;
  border: none;
  border-radius: 5px;
}
</style>