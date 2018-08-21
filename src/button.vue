<template>
  <button class="v-button" v-bind:class="{[`icon-${iconPosition}`]:true}">
    <v-icon v-if="icon" v-bind:name="icon" class="icon"></v-icon>
    <div class="content">
      <slot></slot>
    </div>
  </button>
</template>
<script>
export default {
  props: {
    icon: {},
    iconPosition: {
      type: String,
      default: 'left',
      validator(value){
        return value === 'left' || value === 'right'
      }
    }
  }
};
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
  display:inline-flex;
  vertical-align: middle; //解决对齐问题
  justify-content: center;
  align-items: center;
  &:hover {
    border-color: var(--border-color-hover);
  }
  &:active {
    background: var(--button-active-bg);
  }
  &:focus {
    outline: none;
  }
  > .content {
    order: 2;
  }
  > .icon {
    order: 1;
    margin-right: 0.5em;
  }
  &.icon-right {
    > .content {
      order: 1;
    }
    > .icon {
      order: 2;
      margin-left: 0.5em;
      margin-right: 0;
    }
  }
}
#app {
  margin: 20px;
  display: flex;
  align-items: center;
}
</style>