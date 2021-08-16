<template>
  <main id="content">
    <UpperSection
      :progress="progress"
      :stop="stop"
      :start="start"
      :fileSize="fileSize"
    />
    <hr />
    <BottomSection :progress="progress" :start="start" :isStarted="isStarted" />
  </main>
</template>

<script>
import UpperSection from "./components/UpperSection.vue";
import BottomSection from "./components/BottomSection.vue";
export default {
  components: {
    UpperSection,
    BottomSection,
  },
  data() {
    return {
      progress: 0,
      fileSize: 0,
      isStarted: false,
      increase: "",
    };
  },
  methods: {
    start() {
      this.isStarted = true;
      if (this.progress === 100) this.progress = 0;
      let vm = this;
      let width = 5;

      this.increase = setInterval(() => {
        if (vm.progress >= 100) {
          clearInterval(this.increase);
          return;
        }
        vm.progress += width;
      }, 500);
    },
    stop() {
      clearInterval(this.increase);
    },
  },
};
</script>

<style>
* {
  margin: 0;
  box-sizing: border-box;
}

body {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background: #c2e59c; /* fallback for old browsers */
  background: -webkit-linear-gradient(
    to right,
    #64b3f4,
    #c2e59c
  ); /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(
    to right,
    #64b3f4,
    #c2e59c
  ); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  font-family: Georama, "sans-serif";
}

#content {
  border: 1px solid white;
  padding: 0 20px;
  width: 500px;
  height: 600px;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  background-color: #fff;
  box-shadow: 2px 2px 8px 1px rgba(0, 0, 0, 0.2);
  border-radius: 10px;
}

input[type="text"] {
  background: #fff;
  border: 1px solid #aaa;
  outline: none;
  padding: 4px 7px;
}

input[type="text"]:focus {
  border: 2px solid lightblue;
}
</style>
