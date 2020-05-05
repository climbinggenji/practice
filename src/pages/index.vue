<template>
    <div>
        <Navbar></Navbar>
        <div id="main">
            <Menu></Menu>
            <Content></Content>
        </div>
        <div class="footer">
            <div class="footer-icon">
                <img :src="backSrc" @mouseover="changeImgSrc('_hover')" @mouseleave="changeImgSrc('')">
            </div>
            <div class="footer-text">
                <div class="footer-text-content">Note:When the recovery is done. please exit the recovery mode to use your device normally.</div>
                <button class="footer-text-btn">Exit Recovery Mode</button>
            </div>
            <button class="footer-recover">Recover</button>
        </div>
    </div>
</template>

<script>
import Navbar from "./Navbar.vue";
import Menu from "./Menu.vue";
import Content from "./content.vue";
export default {
  components: {
    Navbar,
    Menu,
    Content
  },
  data() {
    return {
      backSrc: require("@/assets/dback/back_normal.png")
    };
  },
  methods: {
    changeImgSrc(state) {
      if (state === "") {
        this.backSrc = require("@/assets/dback/back_normal.png");
      }
      if (state === "_hover") {
        this.backSrc = require("@/assets/dback/back_hover.png");
      }
    }
  }
};
</script>

<style lang="less" scoped>
#main {
  display: flex;
  flex-wrap: nowrap;
}
.footer {
  display: flex;
  align-items: center;
  padding: 8px 20px;
  border-top: 1px solid #e0e0e0;
  &-icon {
    width: 28px;
    height: 28px;
    cursor: pointer;
  }
  &-text {
    flex-grow: 1;
    display: flex;
    align-items: center;
    &-content {
      padding: 0 20px;
      font-size: 12px;
    }
    &-btn {
      background-color: #fff;
      border-radius: 5px;
      border: 1px solid #41bb8c;
      color: #41bb8c;
      font-size: 12px;
      padding: 5px 10px;
      cursor: pointer;
    }
  }
  &-recover {
    width: 115px;
    font-size: 12px;
    cursor: pointer;
    padding: 8px 0;
    background-color: #00a464;
    color: #fff;
    border-radius: 5px;
    border: none;
  }
}
</style>