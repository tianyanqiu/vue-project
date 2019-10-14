<template>
  <button
    class="v-btn"
    :class="[
{
  primary,
  light,
  success,
  info,
  warning,
  danger,
  dark,
  disabled,
  large,
  normal,
  small,
  outline,
  clear,
  round,
  block,
  full,
  iconLeft,
  iconRight,
  iconOnly
}]"
    :style="style"
    :name="name"
    :large="large"
    :normal="normal"
    :small="small"
    :disabled="disabled"
    :primary="primary"
    :light="light"
    :success="success"
    :info="info"
    :warning="warning"
    :danger="danger"
    :dark="dark"
    :outline="outline"
    :clear="clear"
    :round="round"
    :block="block"
    :full="full"
    :iconLeft="iconLeft"
    :iconRight="iconRight"
    :iconOnly="iconOnly"
    v-on:click="handleClick"
  >
    {{title}}
    <slot />
  </button>
</template>

<script>
export default {
  name: "v-button",
  props: {
    title: {
      type: String,
      default: null
    },
    name: {
      type: String,
      default: null
    },
    customClass: {
      type: String,
      default: null
    },
    disabled: {
      type: Boolean,
      default: false
    },
    large: {
      type: Boolean,
      default: false
    },
    normal: {
      type: Boolean,
      default: false
    },
    small: {
      type: Boolean,
      default: false
    },
    primary: {
      type: Boolean,
      default: false
    },
    light: {
      type: Boolean,
      default: false
    },
    success: {
      type: Boolean,
      default: false
    },
    info: {
      type: Boolean,
      default: false
    },
    warning: {
      type: Boolean,
      default: false
    },
    danger: {
      type: Boolean,
      default: false
    },
    dark: {
      type: Boolean,
      default: false
    },
    outline: {
      type: Boolean,
      default: false
    },
    clear: {
      type: Boolean,
      default: false
    },
    round: {
      type: Boolean,
      default: false
    },
    block: {
      type: Boolean,
      default: false
    },
    full: {
      type: Boolean,
      default: false
    },
    iconLeft: {
      type: Boolean,
      default: false
    },
    iconRight: {
      type: Boolean,
      default: false
    },
    iconOnly: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    handleClick: function() {
      const slot = this.$slots.default && this.$slots.default[0];
      const title = slot ? slot.text : this.title;
      this.$emit("click", title);
    }
  }
};
</script>


<style lang="css" scoped>
.v-btn {
  border: none;
  background: #3f51b5;
  border-radius: 4px;
  font-size: 14px;
  font-weight: 500;
  text-align: center;
  color: white;
  margin: 8px;
  min-width: 88px;
  min-height: 36px;
  box-shadow: 0 2px 2px 0 #3f51b5;
}

.outline {
  border: 1px solid #3f51b5;
  color: #3f51b5;
  background: rgba(0, 0, 0, 0);
  box-shadow: 0 0 0 0;
}

.clear {
  background: rgba(0, 0, 0, 0);
  color: #3f51b5;
  box-shadow: 0 0 0 0 rgba(0, 0, 0, 0);
}

.round {
  border-radius: 64px;
}

.block {
  width: calc(100% - 16px);
}

.full {
  width: 100%;
  border-radius: 0px;
  margin: 8px 0px 8px 0px;
}

.disabled {
  background: rgba(0, 0, 0, 0.12);
  color: rgba(0, 0, 0, 0.38);
  box-shadow: 0 2px 2px 0 rgba(0, 0, 0, 0.12);
}

.small {
  margin: 4.8px 2.4px;
  min-height: 24px;
  min-width: 76px;
  font-size: 12px;
}

.large {
  margin: 4.8px 2.4px;
  min-height: 48px;
  min-width: 100px;
  font-size: 18px;
}

.light {
  background: #f4f4f4;
  color: #000;
  box-shadow: 0 2px 2px 0 #f4f4f4;
}

.success {
  background: #5cb85c;
  box-shadow: 0 2px 2px 0 #5cb85c;
}

.info {
  background: #62b1f6;
  box-shadow: 0 2px 2px 0 #62b1f6;
}

.warning {
  background: #f0ad4e;
  box-shadow: 0 2px 2px 0 #f0ad4e;
}

.danger {
  background: #d9534f;
  box-shadow: 0 2px 2px 0 #d9534f;
}

.dark {
  background: #000;
  box-shadow: 0 2px 2px 0 #000;
}
</style>


