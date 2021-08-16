<template>
  <section class="upper-section">
    <div class="top-section">
      <div class="check-box">
        <div>
          <input id="numeric" type="checkbox" />
          <label for="numeric">Numeric</label>
        </div>

        <div>
          <input id="alpahnumreic" type="checkbox" />
          <label for="alpahnumreic">Alphanumeric</label>
        </div>

        <div>
          <input id="float" type="checkbox" />
          <label for="float">Float</label>
        </div>
      </div>

      <div class="input-size">
        <label>Size of the output file (KB)</label>
        <input type="text" v-model="fileSize" />
      </div>
    </div>
    <button class="start" @click="start">Start</button>
    <button class="stop" @click="stop">Stop</button>
  </section>
</template>

<script>
export default {
  props: {
    start: {
      type: Function,
    },
    stop: {
      type: Function,
    },
    progress: {
      type: Number,
    },
    fileSize: {
      type: Number,
    },
  },
};
</script>

<style scoped>
.top-section {
  margin-bottom: 20px;
  display: flex;
  justify-content: space-between;
}

.check-box {
  display: flex;
  flex-direction: column;
}

.check-box div {
  margin-bottom: 20px;
}

.check-box div input {
  margin-right: 5px;
}

.input-size {
  display: flex;
  flex-direction: column;
}

.input-size label {
  margin-bottom: 10px;
}

#content .upper-section button {
  margin-right: 5px;
  border: none;
  outline: none;
  background: none;
  padding: 20px 30px;
  border-radius: 10px;
  cursor: pointer;
  color: #fff;
  font-weight: bold;
  font-size: 14px;
}

#content .upper-section .start {
  background-color: lightblue;
}

#content .upper-section .start:hover {
  background-color: rgba(173, 216, 230, 0.693);
}

#content .upper-section .stop {
  background-color: rgba(255, 0, 0, 0.604);
}

#content .upper-section .stop:hover {
  background-color: rgba(255, 0, 0, 0.467);
}
</style>