<template>
    <button class="v-button">按钮</button>
</template>
<script>
export default {};
</script>
<style lang="scss">
:root {
  --button-height: 32px;
  --font-size: 14px;
  --button-bg: white;
  --button-active-bg: #eee;
  --border-radius: 4px;
  --color: #333;
  --border-color: #999;
  --border-color-hover: #666;
}
.v-button {
  font-size: var(--font-size);
  height: var(--button-height);
  padding: 0 1em; /*按钮宽度不要写死*/
  border-radius: var(--border-radius);
  border: 1px solid var(--border-color);
  background: var(--button-bg);
  &:hover {
    border-color: var(--border-color-hover);
  }
  &:active {
    background: var(--button-active-bg);
  }
  &:focus {
    outline: none;
  }
}
#app {
  margin: 20px;
}
</style>