<template>
    <div id="checkbox">
        <img @click="stateChange()" :src="src">
    </div>
</template>

<script>
export default {
  props: {
    state: {
      type: Number,
      default: 0
    },
    focus: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      icon0: require("@/assets/dback/check_box_normal2.png"),
      icon1: require("@/assets/dback/check_box_normal.png"),
      icon2: require("@/assets/dback/select.png"),
      icon3: require("@/assets/dback/partial_select.png")
    };
  },
  computed: {
    src() {
      switch (this.state) {
        case 0:
          if (this.focus) {
            return this.icon0;
          }
          return this.icon1;
          break;
        case 1:
          return this.icon2;
          break;
        case 2:
          return this.icon3;
          break;
        default:
          break;
      }
    }
  },
  methods: {
    stateChange() {
      switch (this.state) {
        case 0:
          this.$emit("update:state", 1);
          break;
        case 1:
          this.$emit("update:state", 2);
          break;
        case 2:
          this.$emit("update:state", 0);
          break;
        default:
          break;
      }
    }
  }
};
</script>

<style lang="less" scoped>
#checkbox {
  height: 14px;
  width: 14px;
  img {
    height: 100%;
    width: 100%;
    &:hover {
      cursor: pointer;
    }
  }
}
</style>