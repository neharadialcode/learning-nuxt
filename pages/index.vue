<template>
  <div class="p-10">
    <New />
    <div class="flex">
      <div v-for="(item, index) in tableColor" :key="index">
        <button
          class="px-10 py-5 my-2 mx-1 text-xl font-bold text-white rounded-[10px]"
          :style="{ backgroundColor: `${item.color}` }"
          @click="colorChange(item.color)"
        >
          {{ item.color }}
        </button>
      </div>
    </div>
    <div
      class="w-[200px] h-[200px] bg-black mt-3"
      :style="{ backgroundColor: `${this.isColor}` }"
    ></div>
    <h1 :style="{ color: `${this.isColor}` }" class="text-3xl font-bold py-5">
      Hello World
    </h1>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "IndexPage",
  methods: {
    colorChange(value) {
      this.isColor = value;
    },
  },
  data() {
    return {
      isColor: "",
      tableColor: [
        {
          color: "red",
        },
        {
          color: "blue",
        },
        {
          color: "green",
        },
        {
          color: "pink",
        },
      ],
    };
  },
});
</script>

<style>
.is-right {
  padding-left: 20%;
}
</style>
