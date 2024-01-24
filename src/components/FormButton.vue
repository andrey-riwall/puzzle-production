<template>
  <button type="submit" class="button">
    Change
  </button>
</template>

<script lang='ts'>
import { defineComponent } from 'vue';

export default defineComponent({
  props: {},
  data() {
    return {}
  },
});
</script>

<style lang='scss'>
  .button {
    position: absolute;
    bottom: 50px;
    left: 30px;
    right: 30px;

    padding: 15px 30px;
    background: white;
    border-radius: 15px;
    
    font-family: "JetBrains Mono", sans-serif;
    font-size: 20px;

    margin-top: 10px;
  }
</style>