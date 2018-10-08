<template>
  <div class="
      bg-green
      min-h-screen
    "
  >
    <div class="text-center">
      <img src="./assets/zubin.jpg" alt="">
    </div>

    <h1 class="
        text-white
        font-mono
        text-2xl
        text-center
        p-2
      "
      v-if="win"
    >
      You ARE SMARTER!
    </h1>

    <h1 class="
        text-black
        font-mono
        text-2xl
        text-center
        p-2
      "
      v-else
    >
      Zubin IS SMARTER!
    </h1>

    <div class="text-center">
      <button 
        class="
          font-mono
          text-red
          text-3xl
          cursor-pointer
          p-2
          border-pink-light
          border-4
          rounded-lg
          bg-orange-light
        "
        v-on:click="onRetryClick()"
      >
        Retry!
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    win: Boolean,
  },

  methods: {
    onRetryClick() {
      this.$emit("retry:click");
    },
  },
}
</script>
