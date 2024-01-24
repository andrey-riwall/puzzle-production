<template>
  <section>
    <h2 class="heading">Servers List</h2>
    <ul class="list scroll">
      <ModelItem
        v-for="item in items"
        :key="items.indexOf(item)"
        :item="item"
        @click="choiceItem(item)"
      />
    </ul>
  </section>
</template>

<script lang='ts'>
import { PropType, defineComponent } from 'vue';
import ModelItem from '@/components/ModelItem.vue';
import { Model } from '@/types/types';

export default defineComponent({
  props: {
    items: {
      type: Array as PropType<Model[]>,
      required: true
    }
  },
  emits: {
    "choice_item"(payload: Model) {
      return payload;
    },
  },
  components: {
    ModelItem: ModelItem,
  },
  data() {
    return {}
  },
  methods: {
    choiceItem(item: Model) {
      this.$emit("choice_item", item);
    }
  }
});
</script>

<style scoped lang='scss'>
  section {
    height: 600px;
  }

  .list {
    display: flex;
    flex-direction: column;
    gap: 30px;

    height: 600px;
    padding-right: 5px;

    overflow-y: auto;
  }
</style>