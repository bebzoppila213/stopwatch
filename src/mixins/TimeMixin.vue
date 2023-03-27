

<script>
export default {
  methods: {
    getFormatedTime(hours, minutes, seconds, separator) {
      const resultTime = [this.getFormatedTimeItem(seconds)];
      if (hours > 0) {
        resultTime.unshift(hours, this.getFormatedTimeItem(minutes));
      } else if (minutes > 0) {
        resultTime.unshift(this.getFormatedTimeItem(minutes));
      }
      return resultTime.join(separator);
    },

    getFormatedTimeItem(time) {
      if (time < 10) {
        return `0${time}`;
      }
      return `${time}`;
    },
  },
};
</script>