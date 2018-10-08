<template>
  <div class="
      bg-green
      min-h-screen
    "
  >
    <h1 class="
        text-blue
        font-mono
        text-3xl
        text-center
        p-4
        pt-10
      "
    >
      Are You <span class="text-5xl">Smarter</span> Than <span class="text-5xl">Zubin</span>?
    </h1>

    <h1 class="
        text-white
        font-mono
        text-3xl
        text-center
        p-4
      "
      v-if="win"
    >
      You ARE SMARTER!
    </h1>

    <h1 class="
        text-black
        font-mono
        text-3xl
        text-center
        p-4
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
          p-4
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
