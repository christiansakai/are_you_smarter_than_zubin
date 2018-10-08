<template>
  <div class="
    font-mono
    text-2xl
    font-bold
    text-black
    bg-blue
    border-green-light
    border-4
    rounded-lg
    inline-block
    p-4
    "
  >
    {{display.minutes}}:{{display.seconds}}
  </div>
</template>

<script>
export default {
  props: {
    seconds: Number,
  },

  computed: {
    display() {
      const totalSeconds = this.seconds;

      const minutes = this.padWithZero(
        Math.floor(totalSeconds / 60).toString()
      );

      const seconds = this.padWithZero(
        (totalSeconds % 60).toString()
      );

      return { minutes, seconds };
    }
  },

  methods: {
    padWithZero(digit) {
      if (digit.length === 1) {
        return `0${digit}`;
      }

      return digit;
    }
  },
}
</script>
