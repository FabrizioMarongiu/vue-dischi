<template>
  <main>
    <div class="container" v-if="!loading">
      <Select @send="searchMusic" />
      <div class="row">
        <div
          class="box-card"
          v-for="(element, index) in filterChoice"
          :key="index"
        >
          <Cards :element="element" />
        </div>
      </div>
    </div>
    <Load v-else />
  </main>
</template>

<script>
import axios from "axios";
import Cards from "@/components/Cards.vue";
import Load from "@/components/Load.vue";
import Select from "@/components/Select.vue";

export default {
  name: "Main",
  components: {
    Cards,
    Select,
    Load,
  },
  data() {
    return {
      api: "https://flynn.boolean.careers/exercises/api/array/music",
      musicList: [],
      loading: true,
      scelta: "",
    };
  },
  computed: {
    filterChoice() {
      if (this.scelta.toLowerCase() === "all") {
        return this.musicList;
      }

      return this.musicList.filter((element) => {
        // return console.log(element.genre);
        return element.genre.toLowerCase().includes(this.scelta.toLowerCase());
      });
    },
  },
  created() {
    this.getMusic();
  },
  methods: {
    getMusic() {
      axios
        .get(this.api)
        .then((res) => {
          this.musicList = res.data.response;
          console.log(this.musicList);
          this.loading = false;
        })
        .catch((error) => {
          console.log(error, "Error");
        });
    },
    searchMusic(choice) {
      this.scelta = choice;
      console.log("****", this.scelta);
    },
  },
};
</script>

<style scoped lang="scss">
main {
  background-color: #1d2d3c;
  height: 100%;
  padding: 50px;
}

.row {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
.box-card {
  flex-basis: calc(100% / 8 - 20px);
  height: 270px;
  margin: 10px;
  background-color: #2e3a46;
}
</style>