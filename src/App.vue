<template>
  <div id="app">
    <div :style="{ backgroundColor: randomColor }" class="np-color-preview">
      NightProgrammer.com
    </div>
    <button @click="getRandomColor" class="np-btn">
      Generate random color
    </button>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      randomColor: "#ff0000",
    };
  },
  methods: {
    getRandomColor() {
      this.randomColor = this.generateRandomHexColor();
    },
    generateRandomHexColor() {
      const randomColor =
        "#" + Math.floor(Math.random() * 16777215).toString(16);
      if (randomColor.length !== 7) {
        return this.generateRandomHexColor();
      } else {
        return randomColor;
      }
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.np-color-preview {
  height: 200px;
  width: 200px;
  padding: 6px;
  border-radius: 4px;
  color: #fff;
}
.np-btn {
  margin-top: 12px;
  background: #eee;
  border: 0px;
  padding: 6px 10px;
  border-radius: 4px;
  background: rgb(0, 70, 201);
  color: #fff;
  cursor: pointer;
}
</style>
