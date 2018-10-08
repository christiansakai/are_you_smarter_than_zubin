<template>
  <div class="
      bg-green
      min-h-screen
    "
    v-on:click="onScreenClick()"
  >
    <h1 class="
        text-blue
        font-mono
        text-5xl
        text-center
        p-4
        pt-10
        mb-10
      "
    >
      {{word}}
    </h1>

    <div class="text-center">
      <Time
        v-bind:seconds="seconds" 
      />
    </div>
  </div>
</template>

<script>
import Time from './components/Time.vue';

export default {
  components: {
    Time,
  },

  data() {
    return {
      rounds: 2,
      seconds: 0,
      word: "",
    }
  },

  created() {
    this.resetRound();

    setTimeout(() => {
      this.countdown();
    }, 1000);
  },

  methods: {
    onScreenClick() {
      this.rounds--;

      if (this.rounds === 0) {
        return this.$emit('game:end');
      }

      this.resetRound();
    },

    resetRound() {
      this.seconds = 10;
      this.word = this.chooseRandomNoun();
    },

    chooseRandomNoun() {
      const nouns = [
        "LORD",
        "GOD",
        "MAN",
        "ISRAEL",
        "PEOPLE",
        "KING",
        "SON",
        "MEN",
        "HOUSE",
        "DAY",
        "CHILDREN",
        "LAND",
        "THINGS",
        "HAND",
        "EARTH",
        "SONS",
        "JERUSALEM",      
        "CITY",
        "JESUS",
        "FATHER",
        "NAME",
        "HEART",
        "DAYS",
        "DAVID",
        "MOSES",
        "PLACE",
        "TIME",
        "JUDAH",
        "WORD",
        "EVIL",
        "HEAVEN",
        "BRETHREN",
        "WORDS",
        "FIRE",
        "EGYPT",
        "THING",
        "LAW",
        "FATHERS",
        "LIFE",
        "HANDS",
        "EYES",
        "FEAR",
        "VOICE",
        "CHRIST",
        "PRIEST",
        "SPIRIT",
        "SERVANTS",
        "SOUL",
        "SERVANT",
        "GLORY",
        "PEACE",
        "GOLD",
        "MOUTH",
        "DEATH",
        "PRIESTS",
        "CITIES",
        "SWORD",
        "SIN",
        "FACE",
        "WATER",
        "SEA",
        "LEFT",
        "WORK",
        "BLOOD",
        "WIFE",
        "FLESH",
        "WOMAN",
        "BROTHER",
        "HEAD",
        "YEAR",
        "SIDE",
        "END",
        "RIGHT",
        "KINGDOM",
        "NATIONS",
        "POWER",
        "SIGHT",
        "ALTAR",
        "JACOB",
        "KINGS",
        "ENEMIES",
        "CONGREGATION",
        "BREAD",
        "NIGHT",
        "SILVER",
        "WORLD",
        "WISDOM",
        "JUDGMENT",
        "JEWS",
        "MULTITUDE",
        "LOVE",
        "DAUGHTER",
        "SAUL",
        "REST",
        "AARON",
        "WILDERNESS",
        "CHIEF",
        "COVENANT",
        "TABERNACLE",
        "TEMPLE",
      ];

      const randomIndex = Math.floor(Math.random() * nouns.length);
      return nouns[randomIndex];
    },

    countdown() {
      if (this.seconds === 0) {
        this.rounds--;

        if (this.rounds === 0) {
          return this.$emit('game:end');
        }

        this.resetRound();
      } else {
        this.seconds--;
      }

      setTimeout(() => {
        this.countdown();
      }, 1000);
    },
  },
}
</script>
