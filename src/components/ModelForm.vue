<template>
  <section>
    <h2 class="heading">Model Form</h2>
    <form
      action="#"
      class="form card"
      autocomplete="off"
      ref="form"
      @submit.prevent="submit"
    >
      <FormInput
        v-for="input in inputs"
        :key="inputs.indexOf(input)"
        :heading="input"
        :value="item[input]"
        :disabled="input === 'customer_id' ? true : false"
      />
      <FormButton />
    </form>
  </section>
</template>

<script lang='ts'>
import { Model } from '@/types/types';
import { PropType, defineComponent } from 'vue';
import FormInput from '@/components/FormInput.vue';
import FormButton from '@/components/FormButton.vue';

interface Input extends Model {
  name: keyof Model;
  value: string
}

export default defineComponent({
  props: {
    item: {
      type: Object as PropType<Model>,
      required: true
    },
  },
  components: {
    FormInput: FormInput,
    FormButton: FormButton,
  },
  emits: {
    "update_list"(payload: Model) {
      return payload;
    },
  },
  data() {
    return {}
  },
  methods: {
    submit() {
      const newItem = {} as Model;
      // @ts-ignore
      const inputs : Input[] = Array.from(this.$refs.form.elements).filter((input) => input.value);
      inputs.forEach((input : Input) => {
        newItem[input.name] = input.value;
      });
      this.$emit('update_list', newItem);
    }
  },
  computed: {
    inputs() : Array<keyof Model> {
      return Object.keys(this.item) as Array<keyof Model>;
    }
  }
});
</script>

<style scoped lang='scss'>
  .form {
    position: relative;

    display: flex;
    flex-direction: column;
    gap: 20px;

    height: 600px;
    padding-bottom: 126px;
    overflow: auto;
  }

</style>