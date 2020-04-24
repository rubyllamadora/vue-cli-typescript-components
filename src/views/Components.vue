<template>
  <div class="components">
    <button class="btn btn--default txt--center" @click="showSpinner">
      <ProgressLoader v-if="isSpinnerVisible" class="progress-loader--small"/>&nbsp;Submit
    </button>
  </div>
</template>

<style lang="scss" scoped>
.btn {
  border: 2px solid black;
  background-color: white;
  color: black;
  padding: 14px;
  font-size: 16px;
  cursor: pointer;
  height: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.txt--center {
  margin: 0 auto;
}

/* Green */
.btn--success {
  border-color: #4caf50;
  color: green;

  &:hover {
    background-color: #4caf50;
    color: white;
  }
}

/* Gray */
.btn--default {
  border-color: #e7e7e7;
  color: black;
  &:hover {
    background: #e7e7e7;
  }
}
</style>

<script lang="ts">
import { Component, Emit, Vue } from "vue-property-decorator";
import ProgressLoader from "@/components/ProgressLoader.vue";

@Component({
  components: { ProgressLoader }
})
export default class Components extends Vue {
  isSpinnerVisible = false;

  @Emit()
  showSpinner() {
    this.isSpinnerVisible = true;
  }
}
</script>
