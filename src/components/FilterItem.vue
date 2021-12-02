<template>
  <div>
    <input type="checkbox"
           :name="title"
           :value="value">
    <label :for="value">
      {{ title }}
    </label><br>
  </div>
</template>

<script>

import {defineComponent} from "vue";

export default defineComponent({
  props: {
    title: {
      type: String,
      default: ''
    },
    value: {
      type: String,
      default: ''
    },
    checked: {
      type: Boolean,
      default: false
    }
  },

  setup(props, { emit }) {

  }
})
</script>

<style scoped>

</style>
