

<script>
import TimeMixinVue from "mixins/TimeMixin.vue";

export default {
  data: () => {
    return {
      stopwatch: { hours: 0, minutes: 0, seconds: 0 },
      isActive: false,
      timer: null,
    };
  },

  mixins: [TimeMixinVue],

  methods: {
    tick() {
      this.stopwatch.seconds += 1;
      if (this.stopwatch.seconds >= 60) {
        this.stopwatch.seconds = 0;
        this.stopwatch.minutes += 1;
      }
      if (this.stopwatch.minutes >= 60) {
        this.stopwatch.seconds = 0;
        this.stopwatch.minutes = 0;
        this.stopwatch.hours += 1;
      }
    },

    start() {
      this.isActive = true;
      this.timer = setInterval(() => this.tick(), 1000);
    },

    pause() {
      this.isActive = false;
      clearInterval(this.timer);
    },

    reset() {
      this.stopwatch = { minutes: 0, seconds: 0, hours: 0 };
      clearInterval(this.timer);
      this.isActive = false;
    },

    getTime() {
      return this.getFormatedTime(
        this.stopwatch["hours"],
        this.stopwatch["minutes"],
        this.stopwatch["seconds"],
        ":"
      );
    },
  },
};
</script>