<template>
  <div class="block" v-if="showBlock">Click Me</div>
</template>

<script>
import { onUnmounted } from "vue";
export default {
  props: ["delay"],
  data() {
    return {
      showBlock: false,
    };
  },
  mounted() {
    console.log("Component mounted");
    setTimeout(() => {
      this.showBlock = true;
      console.log(this.delay);
    }, this.delay);
  },
  updated() {
    console.log("Component updated");
  }, 
  unmounted() {
    console.log("Component unMounted");
  }, 
};
</script>

<style>
.block {
  width: 400px;
  border-radius: 20px;
  background-color: #0faf87;
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>