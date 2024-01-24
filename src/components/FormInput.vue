<template>
  <label class="label" :for="heading">
    <h3 class="form-heading">
      {{ heading }}
    </h3>
    <input
      class="input"
      type="text"
      :placeholder="heading"
      :name="heading"
      :value="value"
      :id="heading"
      :disabled="disabled"
      required
      v-if="heading !== 'server_type'"
    />
    <select
      class="select input"
      :name="heading"
      :id="heading"
      :value="value"
      required
      v-else
    >
      <option
        v-for="option in options"
        :key="options.indexOf(option)"
        :value="option"
      >
        {{ option }}
      </option>
    </select>
  </label>
</template>

<script lang='ts'>
import { defineComponent } from 'vue';

export default defineComponent({
  props: {
    heading: {
      type: String,
      required: true
    },
    value: {
      type: String
    },
    disabled: {
      type: Boolean,
    },
  },
  data() {
    return {
      options: [
        'type1',
        'type2',
        'type3'
      ]
    }
  },
});
</script>

<style scoped lang='scss'>
  .label {
    display: block;

    * {
      font-family: "JetBrains Mono", sans-serif;
    }
  }

  .form-heading {
    font-size: 24px;

    margin-bottom: 5px;
  }

  .input {
    width: 100%;
    padding: 15px 30px;
    border-radius: 15px;

    background: white;

    font-size: 20px;

    &[disabled] {
      cursor: not-allowed;
    }
  }
</style>