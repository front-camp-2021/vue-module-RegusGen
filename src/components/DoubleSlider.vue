<template>
  <div class="range-slider">
    <p class="filter-name">
      {{ filterName }}
    </p>
    <span data-element="from">{{ min }}</span>
    <div class="range-slider__inner">
      <span class="range-slider__progress"
            style="left: 0; right: 0" />
      <span class="range-slider__thumb-left"
            style="left: 0" />
      <span class="range-slider__thumb-right"
            style="right: 0" />
    </div>
    <span data-element="to">{{ max }}</span>
  </div>
</template>

<script>
import {defineComponent} from "vue";

export default defineComponent({
  components: {

  },

  props: {
    filterName: {
      type: String,
      default: ''
    },
    min: {
      type: Number,
      default: 0
    },
    max: {
      type: Number,
      default: 0
    },
  },

  setup (props, { emit }) {

  }
})
</script>

<style scoped>
.range-slider__inner {
  position: relative;
  display: inline-block;
  width: 100%;
  height: 4px;
  margin: 10px 14px;
  background: #cfebfc;
  box-shadow: 0 0 1px #c2cfe0;
  user-select: none;
}

.range-slider__thumb-right,
.range-slider__thumb-left {
  position: absolute;
  top: 50%;
  margin-top: -9px;
  height: 18px;
  width: 6px;
  /*background: left center no-repeat;*/
  background-size: cover;
  cursor: pointer;
}

/* cursor over all slider, so that if the cursor moves out of the thumb, it's still grabbing */
.range-slider_dragging,
.range-slider_dragging .range-slider__thumb-right,
.range-slider_dragging .range-slider__thumb-left {
  cursor: grabbing;
}

.range-slider__thumb-left {
  left: 0;
  margin-left: -6px;
}

.range-slider__thumb-right {
  right: 0;
  transform: rotate(180deg);
  margin-right: -6px;
}

.range-slider__progress {
  background: #109cf1;
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  z-index: 1;
}

.range-slider {
  position: relative;
  display: flex;
  flex-direction: row;
  align-items: center;
  padding-right: 60px;
  margin-right: 40px;
}

.range-slider > span {
  font-weight: 700;
  font-size: 16px;
  line-height: 24px;
  color: #707683;
  width: 60px;
  position: absolute;
  top: 50%;
  transform: translate(0, -50%);
}

.range-slider > span:first-child {
  text-align: right;
  left: 0;
}

.range-slider > span:last-child {
  right: 0;
}

.filter-name {
  padding-bottom: 40px;
}

</style>
