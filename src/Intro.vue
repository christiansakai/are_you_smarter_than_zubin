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
        mb-10
      "
    >
      Are You <span class="text-5xl">Smarter</span> Than <span class="text-5xl">Zubin</span>?
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
        v-on:click="onStartClick()"
      >
        Ofc I am!
      </button>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    onStartClick() {
      this.$emit("start:click");
    },
  },
}
</script>
