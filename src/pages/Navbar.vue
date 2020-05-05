<template>
  <div>
    <div id="navbar">
      <div class="left">
        <div class="left-img">
          <img style="height:40px; width:40px" src="@/assets/dback/d-back_50.png">
        </div>
        <span class="left-text">iMyFone D-Back(Andriod)</span>
      </div>
      <div class="right">
        <div class="user">
          <img :src="registerSrc" @mouseover="changeImgSrc(0, '_hover')" @mouseleave="changeImgSrc(0, '')">
        </div>
        <div class="divide"></div>
        <div class="operate">
          <img :src="feedbackScr" @mouseover="changeImgSrc(1, '_hover')" @mouseleave="changeImgSrc(1, '')">
          <img :src="menuSrc" @mouseover="changeImgSrc(2, '_hover')" @mouseleave="changeImgSrc(2, '')">
          <img :src="minimizeSrc" @mouseover="changeImgSrc(3, '_hover')" @mouseleave="changeImgSrc(3, '')">
          <img :src="closeSrc" @mouseover="changeImgSrc(4, '_hover')" @mouseleave="changeImgSrc(4, '')">
        </div>
      </div>
    </div>
    <div id="top">
      <div class="left">
        <div class="icon">
          <img src="@/assets/dback/phoneicon.png">
        </div>
        <div class="text">Samsung Glaxy 10</div>
        <div class="taggou">
          <img src="@/assets/dback/topgou.png">
        </div>
      </div>
      <div class="right">
        <div class="select">
          <Select :list="list" :value="val"></Select>
        </div>
        <div class="search">
          <Input></Input>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Select from "./components/Select.vue";
import Input from "./components/Input.vue";

export default {
  name: "Navbar",
  components: {
    Select,
    Input
  },
  data() {
    return {
      registerSrc: require("@/assets/dback/register.png"),
      feedbackScr: require("@/assets/dback/feedback.jpg"),
      menuSrc: require("@/assets/dback/menu.jpg"),
      minimizeSrc: require("@/assets/dback/minimize.jpg"),
      closeSrc: require("@/assets/dback/close.jpg"),
      list: [
        {
          id: 1,
          name: "show all(80)"
        },
        {
          id: 2,
          name: "show all(70)"
        },
        {
          id: 3,
          name: "show all(50)"
        }
      ],
      val: {
        id: 1,
        name: "show all(80)"
      }
    };
  },
  methods: {
    changeImgSrc(tag, state) {
      switch (tag) {
        case 0:
          this.registerSrc = require(`@/assets/dback/register${state}.png`);
          break;
        case 1:
          this.feedbackScr = require(`@/assets/dback/feedback${state}.jpg`);
          break;
        case 2:
          this.menuSrc = require(`@/assets/dback/menu${state}.jpg`);
          break;
        case 3:
          this.minimizeSrc = require(`@/assets/dback/minimize${state}.jpg`);
          break;
        case 4:
          this.closeSrc = require(`@/assets/dback/close${state}.jpg`);
          break;
        default:
          break;
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less" scoped>
#navbar {
  display: flex;
  justify-content: space-between;
  padding: 10px 20px;
  .left {
    height: 40px;
    display: flex;
    align-items: center;
    &-text {
      line-height: 40px;
      padding-left: 10px;
    }
  }
  .right {
    display: flex;
    align-items: center;
    .user {
      img {
        height: 35px;
        width: 35px;
        cursor: pointer;
      }
    }
    .divide {
      height: 35px;
      border-left: 1px solid #e0e0e0;
      margin: 0 20px;
    }
    .operate {
      img {
        width: 25px;
        height: 25px;
        margin: 0 10px;
        cursor: pointer;
      }
    }
  }
}

#top {
  height: 45px;
  background-image: url("../assets/dback/topbackground.jpg");
  background-size: 100% 100%;
  display: flex;
  flex-wrap: nowrap;

  .left {
    height: 100%;
    width: 215px;
    display: flex;
    align-items: center;
    border-right: 1px solid #e0e0e0;
    justify-content: space-between;
    padding: 0 20px 0 25px;
    .icon {
      height: 25px;
    }
    .text {
      color: #fff;
      font-size: 12px;
      padding-left: 10px;
    }
    .taggou {
      height: 14px;
      img {
        vertical-align: top;
        width: 14px;
        height: 14px;
      }
    }
  }

  .right {
    width: 835px;
    display: flex;
    align-items: center;
    padding: 0 20px;
    justify-content: space-between;
  }
}
</style>
