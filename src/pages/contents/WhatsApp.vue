<template>
    <div id="whatsApp">
        <div class="left">
            <div class="item" v-for="(item, index) in infoList" :key="index" :class="{isSelect: item.isSelect}">
                <div class="icon">
                    <img :src="infoSrc(item.isDeleted)">
                </div>
                <div class="detail">
                    <div class="top">
                        <div class="title" @click="change(item)">
                            truemoveh
                        </div>
                        <div class="time">
                            09/21/2019 05:50:24
                        </div>
                    </div>
                    <div class="text">
                        TruemoveH has upgraded jslkdfjlkasdjfkldasjfklasdjfklsdjkl
                    </div>
                </div>
                <CheckBox :state.sync="item.state" :focus="item.isSelect"></CheckBox>
            </div>
        </div>
        <div class="right">
            <Msg></Msg>
        </div>
    </div>
</template>

<script>
import CheckBox from "./../components/CheckBox.vue";
import Msg from "./msg.vue";
export default {
  components: {
    CheckBox,
    Msg
  },
  data() {
    return {
      infoList: [
        {
          isDeleted: true,
          state: 0,
          isSelect: true
        },
        {
          isDeleted: true,
          state: 0,
          isSelect: false
        },
        {
          isDeleted: false,
          state: 0,
          isSelect: false
        },
        {
          isDeleted: false,
          state: 0,
          isSelect: false
        },
        {
          isDeleted: false,
          state: 0,
          isSelect: false
        },
        {
          isDeleted: false,
          state: 0,
          isSelect: false
        },
        {
          isDeleted: false,
          state: 0,
          isSelect: false
        },
        {
          isDeleted: false,
          state: 0,
          isSelect: false
        },
        {
          isDeleted: false,
          state: 0,
          isSelect: false
        },
        {
          isDeleted: false,
          state: 0,
          isSelect: false
        },
        {
          isDeleted: false,
          state: 0,
          isSelect: false
        },
        {
          isDeleted: false,
          state: 0,
          isSelect: false
        },
        {
          isDeleted: false,
          state: 0,
          isSelect: false
        }
      ]
    };
  },
  computed: {
    infoSrc: function() {
      return function(val) {
        let text = "";
        if (val) {
          text = "_deleted";
        }
        return require(`@/assets/dback/user${text}.png`);
      };
    }
  },
  methods: {
    change(item) {
      if (item.isSelect) {
        return;
      } else {
        this.infoList.forEach(element => {
          element.isSelect = false;
        });
        item.isSelect = true;
      }
    }
  }
};
</script>

<style lang="less" scoped>
#whatsApp {
  display: flex;
  height: 540px;
  .left {
    width: 430px;
    overflow-y: scroll;
    .item {
      height: 60px;
      font-size: 10px;
      display: flex;
      flex-wrap: nowrap;
      align-items: center;
      padding: 0 20px;
      border-top: 1px solid #e0e0e0;
      .icon {
        height: 44px;
        width: 44px;
        img {
          height: 100%;
          width: 100%;
        }
      }
      .detail {
        flex-grow: 1;
        padding: 0 20px 0 5px;
        line-height: 20px;
        .top {
          display: flex;
          justify-content: space-between;
          .title {
            white-space: nowrap;
            overflow: hidden;
            width: 150px;
            text-overflow: ellipsis;
            font-weight: 500;
            &:hover {
              text-decoration-line: underline;
              cursor: pointer;
            }
          }
          .time {
            color: #999;
          }
        }
        .text {
          color: #999;
          white-space: nowrap;
          overflow: hidden;
          width: 150px;
          text-overflow: ellipsis;
        }
      }
    }
    .isSelect {
      .detail {
        .top {
          .title {
            color: #00a464;
          }
          .time {
            color: #72cdaa;
          }
        }
        .text {
          color: #72cdaa;
        }
      }
    }
  }
  .right {
    flex-grow: 1;
    border-left: 1px solid #e0e0e0;
  }
}
</style>