<template>
  <div class="icon-wrapper">
    <svg class="icon" :width="width" :height="height">
      <use v-bind="{ 'xlink:href': '/solid.svg#' + name }" />
    </svg>
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "BaseIcon",
  props: {
    name: String,
    width: {
      type: [Number, String],
      default: 24,
    },
    height: {
      type: [Number, String],
      default: 24,
    },
  },
};
</script>

<style scoped>
.icon-wrapper {
  display: inline-flex;
  align-items: center;
  color: rgba(0, 0, 0, 0.7);
  font-size: 1rem;
  font-weight: 800;
}
.icon {
  stroke: currentColor;
  stroke-width: 2;
  stroke-linecap: round;
  stroke-linejoin: round;
  fill: rgb(0, 0, 0, 0.7);
  margin-right: 6px;
}
</style>
