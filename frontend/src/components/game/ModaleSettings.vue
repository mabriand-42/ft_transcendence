<script>
import PowerUps from "./PowerUps.vue";
export default {
  name: "ModaleSettings",
  components: {
    powerups: PowerUps,
  },
  props: ["toggleModaleSettings", "launch"],
  emit: ["close"],
  created() {
    this.$emit("paddleSizeChange", this.paddleSize);
    this.$emit("ballSpeedChange", this.ballSpeed);
    return;
  },
  methods: {
    updatePaddleSize: function (variable) {
      this.paddleSize = variable;
      this.$emit("paddleSizeChange", this.paddleSize);
      return;
    },
    updateBallSpeed: function (variable) {
      this.ballSpeed = variable;
      this.$emit("ballSpeedChange", this.ballSpeed);
      return;
    },
    close: function () {
      this.$emit("close");
    }
  },
};
</script>

<template>
  <div class="bloc_modale">
    <div class="overlay"></div>
    <div class="modale card">
       <div
        @click="close()"
        type="button"
        class="btn-close-modale btn"
      >
        <i class="fa-solid fa-xmark fa-2x"></i>
      </div>
      <h2 style="padding-top: 10px">
        <u style="text-shadow: 0 0 0.125em hsl(0 0% 100% / 0.3), 0 0 0.45em currentColor;">Start a game</u>
      </h2>
      <powerups
        @paddleSizeChange="updatePaddleSize"
        @ballSpeedChange="updateBallSpeed"
      />
      <button
        @click=""
        type="button"
        class="mod-btn mod-btn-blue"
        style="width: 75%; margin: auto;"
      >
        START
      </button>
    </div> 
  </div>
</template>

<style>
</style>