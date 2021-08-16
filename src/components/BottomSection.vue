<template>
  <section class="bottom-section">
    <div class="counter">
      <div>
        <label>Counter 1 (Numeric)</label>
        <input type="text" />
      </div>

      <div>
        <label>Counter 2 (Alphanumeric)</label>
        <input type="text" />
      </div>

      <div>
        <label>Counter 3 (Float)</label>
        <input type="text" />
      </div>
    </div>
    <button class="generate">Generate Report</button>
    <div v-if="isStarted" class="progress">
      <div :style="{ width: progress + '%' }" class="progress-bar">
        {{ progress }}%
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    progress: {
      type: Number,
    },
    isStarted: {
      type: Boolean,
    },
  },
};
</script>


<style scoped>
.bottom-section .counter div {
  display: flex;
  justify-content: space-between;
  margin-bottom: 15px;
}

.generate {
  background-color: lightgreen;
  padding: 10px 80px;
  border-radius: 10px;
  border: none;
  outline: none;
  cursor: pointer;
  color: #fff;
  font-weight: bold;
  font-size: 14px;
  margin-top: 10px;
}

.generate:hover {
  background-color: rgba(144, 238, 144, 0.844);
}

.bottom-section {
  display: flex;
  flex-direction: column;
}

.progress {
  width: 100%;
  height: 50px;
  background-color: #eee;
  border-radius: 50px;
  margin-top: 20px;
}

.progress-bar {
  height: 100%;
  background-color: lightblue;
  border-radius: 50px;
  text-align: center;
  padding-top: 15px;
}
</style>