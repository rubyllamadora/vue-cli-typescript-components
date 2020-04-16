<template>
  <div class="progress-loader">
    <svg
      class="progress-loader__spinner progress-loader--primary"
      viewBox="0 0 50 50"
    >
      <circle
        class="path"
        cx="25"
        cy="25"
        r="20"
        fill="none"
        stroke-width="5"
      ></circle>
    </svg>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class ProgressLoader extends Vue {
  @Prop({ default: "indeterminate" }) private type!: string;
}
</script>

<style lang="scss" scoped>
/** https://material.io/resources/color/#!/?view.left=0&view.right=0&secondary.color=eaeaea&primary.color=7B1FA2 */
$color-primary: #7b1fa2;
$color-primary--light: #ae52d4;
$color-primary--dark: #4a0072;
$color-secondary: #eaeaea;
$color-secondary--light: #ffffff;
$color-secondary--dark: #b8b8b8;

.progress-loader__spinner {
  animation: rotate 2s linear infinite;
  z-index: 2;
  position: absolute;
  top: 50%;
  left: 50%;
  margin: -25px 0 0 -25px;
  width: 50px;
  height: 50px;

  & .path {
    stroke: hsl(210, 70, 75);
    stroke-linecap: round;
    animation: dash 1.5s ease-in-out infinite;
  }
}

.progress-loader--primary {
  & .path {
    stroke: $color-primary;
  }
}

@keyframes rotate {
  100% {
    transform: rotate(360deg);
  }
}

@keyframes dash {
  0% {
    stroke-dasharray: 1, 150;
    stroke-dashoffset: 0;
  }
  50% {
    stroke-dasharray: 90, 150;
    stroke-dashoffset: -35;
  }
  100% {
    stroke-dasharray: 90, 150;
    stroke-dashoffset: -124;
  }
}
</style>
