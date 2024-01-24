<template>
  <li class="item card">
    {<br>
    &nbsp; customer_id: {{ item.customer_id }},<br>
    &nbsp; server_name: {{ item.server_name }},<br>
    &nbsp; server_type: {{ item.server_type }}<br>
    }
  </li>
</template>

<script lang='ts'>
import { Model } from '@/types/types';
import { PropType, defineComponent } from 'vue';

export default defineComponent({
  props: {
    item: {
      type: Object as PropType<Model>,
      required: true
    }
  },
});
</script>

<style scoped lang='scss'>
  .item {
    width: 100%;

    cursor: pointer;
    font-family: "JetBrains Mono", sans-serif;
  }
</style>