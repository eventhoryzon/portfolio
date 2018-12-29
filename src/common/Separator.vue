<template>
  <div class="separator-container"
    :style="`--separator-color: ${color}`">
    <div class="separator">❅ ❆ ❅
  </div>
  </div>
</template>

<script>
export default {
  name: 'separator',
  props: {
    color: {
      default: getComputedStyle(document.body).getPropertyValue('--separator-color') || 'white',
      type: String,
    },
  },
};
</script>

<style lang="scss" scoped>
  .separator-container {
    text-align: center;
    position: relative;
    user-select: none;
    pointer-events: none;
    font-size: 20px;
  }

  .separator {
    align-items: center;
    color: var(--separator-color);
    margin: 0 auto 0.5em;
    width: 10em;

    &:before,
    &:after {
      display: block;
      width: 30%;
      content: " ";
      margin-top: 15px;
      border: 0.5px solid var(--separator-color);
    }

    &:before {
      float: left;
    }

    &:after {
      float: right;
    }
  }
</style>
