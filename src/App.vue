<template>
  <div>
    <Intro 
      v-if="state === 'start'"
      v-on:start:click="onStartClick()"
    />
    <Game 
      v-if="state === 'game'"
      v-on:game:end="onGameEnd()"
    />
    <Outro 
      v-if="state === 'end'"
      v-on:retry:click="onRetryClick()"
    />
  </div>
</template>

<script>
import Intro from './Intro';
import Game from './Game';
import Outro from './Outro';

export default {
  components: {
    Intro,
    Game,
    Outro,
  },

  data() {
    return {
      state: 'start',
    }
  },

  methods: {
    onStartClick() {
      this.state = 'game';
    },

    onGameEnd() {
      this.state = 'end';
    },

    onRetryClick() {
      this.state = 'start';
    },
  },
}
</script>
