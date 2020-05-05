<template>
    <div class="xbsjselect">
        <div class="xbsjselect-selectdiv" @click="selectClick">
            <span class="xbsjselect-selectText">{{currentValue}}</span>
            <button class="xbsjselect-selectButton"></button>
        </div>
        <ul class="xbsjselect-selectOption" v-show="selectshow">
            <li v-for="(ct,index) in listdata" :key="index" @click="selectName(ct)">
                <span>{{ ct.name }}</span>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
  name: "Select",
  props: {
    list: {
      type: Array,
      default: []
    },
    value: ""
  },
  data() {
    return {
      selectshow: false,
      currentValue: this.value.name
    };
  },
  computed: {
    listdata() {
      return this.list;
    }
  },
  methods: {
    selectClick() {
      this.selectshow = !this.selectshow;
    },
    selectName(value) {
      this.currentValue = value.name;
      this.selectshow = false;
    }
  },
  watch: {
    currentValue(val, old) {
      this.$emit("input", val);
    }
  }
};
</script>

<style lang="less" scoped>
.xbsjselect {
  position: relative;
  width: 175px;
  &-selectdiv {
    display: inline-block;
    width: 100%;
    background: rgba(255, 255, 255, 0.5);
    height: 28px;
    position: relative;
    text-align: left;
    line-height: 28px;
    cursor: pointer;
    left: -2px;
    top: 2px;
    border-radius: 3px;
  }
  &-selectText {
    padding-left: 20px;
    font-size: 12px;
    color: #14ac72;
  }
  &-selectButton {
    width: 12px;
    height: 10px;
    border: none;
    background: url("../../assets/dback/open.png") no-repeat;
    background-size: contain;
    cursor: pointer;
    float: right;
    margin-right: 20px;
    margin-top: 10px;
    outline: none;
  }
  &-selectOption {
    width: 100%;
    height: 80px;
    background: #80ddc0;
    border-radius: 0px 0px 4px 4px;
    list-style: none;
    overflow: auto;
    z-index: 1;
    position: absolute;
    li {
      width: 100%;
      height: 20px;
      font-size: 14px;
      color: #fff;
      line-height: 20px;
      cursor: pointer;
      span {
        display: inline-block;
        height: 20px;
        position: relative;
        left: 11px;
      }
      &:hover {
        background: rgba(107, 107, 107, 1);
      }
    }
  }
}
</style>