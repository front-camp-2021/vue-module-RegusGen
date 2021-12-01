<template>
  <div class="category set-font">
    <p class="nameCategory set-font">
      {{ title }}
    </p>
    <div class="listCategory">
      <form>
        <FilterItem
          v-for="item of list"
          :key="item.value"
          :title="item.title"
          :value="item.value" />
      </form>
    </div>
  </div>
</template>

<script>
import FilterItem from "./FilterItem";
import {defineComponent} from "vue";

export default defineComponent({
  components: {
    FilterItem
  },
  props: {
    title: {
      type: String,
      default: ''
    },
    list: {
      type: Array,
      default: () => []
    },
    selected: {
      type: Array,
      default: () => []
    },
    isInList: {
      type: Boolean,
      default: false
    },
  },
  setup(props, { emit }) {

  }
})
</script>>

<style scoped>

</style>
