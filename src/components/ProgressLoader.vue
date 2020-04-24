<template>
  <div class="progress-loader"/>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class ProgressLoader extends Vue {
  @Prop({ default: "indeterminate" }) private type!: string;
}
</script>

<style lang="scss" scoped>
.progress-loader {
  border: 10px solid $color-primary--light;
  border-top: 10px solid $color-secondary;
  border-radius: 50%;
  max-width: 50px;
  max-height: 50px;
  -webkit-animation: spin 1s linear infinite; /* Safari */
  animation: spin 1s linear infinite;
  display: inline-block;
  margin-right: 5px;
}

.progress-loader--small {
  width: 16px;
  height: 16px;
  border: 5px solid $color-primary--light;
  border-top: 5px solid $color-secondary;
}

/* Safari */
@-webkit-keyframes spin {
  0% {
    -webkit-transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(360deg);
  }
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>
