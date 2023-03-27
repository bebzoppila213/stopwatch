<template>
  <div class="wrapper">
    <div class="stopwatch-inner">
      <Stopwatch v-for="item in stopwatches" :key="item.id" />
      <StopwatchAdd @stopwatchAddClick="addStopwatch" />
    </div>
  </div>
</template>

<script>
import Stopwatch from "components/Stopwatch.vue";
import StopwatchAdd from "components/StopwatchAdd.vue";

export default {
  components: {
    Stopwatch,
    StopwatchAdd,
  },

  data: () => {
    return {
      stopwatches: [{ id: 1 }],
    };
  },

  methods: {
    addStopwatch() {
      this.stopwatches.push({ id: Math.floor(Math.random() * 123) });
    },
  },
};
</script>

