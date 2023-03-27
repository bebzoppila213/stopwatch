
<template>
  <div class="stopwatch" :class="{ 'stopwatch--active': isActive }">
    <div class="stopwatch-header"> {{ getTime() }}</div>
    <div :class="{ 'stopwatch-line--active': isActive }" class="line stopwatch-line"></div>
    <div class="stopwatch-footer">
      <StopwatchMenu
        v-if="!isActive"
        :rightBtnImg="resetGrayImg"
        :leftBtnImg="startImg"
        @leftBtnСlick="start"
        @rightBtnСlick="reset"
      />
      <StopwatchMenu
        @rightBtnСlick="reset"
        @leftBtnСlick="pause"
        v-else
        :rightBtnImg="resetImg"
        :leftBtnImg="pauseImg"
      />
    </div>
  </div>
</template>

<script>
import StopWatchMenuImages from "mixins/StopwatchMenuImages.vue";
import StopwatchMenu from "components/StopwatchMenu.vue";
import StopwatchMixin from "mixins/StopwatchMixin.vue";

export default {
  components: {
    StopwatchMenu,
  },
  mixins: [StopWatchMenuImages, StopwatchMixin],
  
  methods: {
  },
};
</script>