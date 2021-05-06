<template>
  <main>
    <div class="container">
      <div class="row">
        <Cards
          v-for="(element, index) in musicList"
          :key="index"
          :element="element"
        />
      </div>
    </div>
  </main>
</template>

<script>
import axios from "axios";
import Cards from "@/components/Cards.vue";

export default {
  name: "Main",
  components: {
    Cards,
  },
  data() {
    return {
      api: "https://flynn.boolean.careers/exercises/api/array/music",
      musicList: [],
      loading: true,
    };
  },
  created() {
    this.getMusic();
  },
  methods: {
    getMusic() {
      axios
        .get(this.api)
        .then((res) => {
          this.musicList = res.data;
          loading = false;
        })
        .catch((error) => {
          console.log(error, "Error");
        });
    },
  },
};
</script>

<style scoped lang="scss">
main {
  background-color: #1d2d3c;
  height: 100%;
  padding: 100px;
}

.row {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>