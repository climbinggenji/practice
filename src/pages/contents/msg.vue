<template>
    <div id="msg">
        <div class="top">To:grab</div>
        <div class="contain">
            <div class="item" v-for="(item, index) in infoList" :key="index"  :class="{isRight: item.type}">
                <div class="info-left">
                    <div class="info-left-top">
                        <div class="time">09/21/2019 05:50:24</div>
                        <div class="icon" v-if="item.isDeleted">
                            <img src="@/assets/dback/deleted2.png">
                        </div>
                    </div>
                    <div class="text-line">
                        <div class="text">
                            Your Crab Activation Code (GAC) is 2381
                        </div>
                    </div>
                </div>
                <div class="info-right">
                    <CheckBox  :state.sync="item.state"></CheckBox>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import CheckBox from "./../components/CheckBox.vue";
export default {
  components: {
    CheckBox
  },
  data() {
    return {
      infoList: [
        {
          type: 0,
          isDeleted: true,
          state: 1
        },
        {
          type: 1,
          isDeleted: true,
          state: 1
        },
        {
          type: 0,
          isDeleted: false,
          state: 0
        },
        {
          type: 1,
          isDeleted: false,
          state: 0
        },
        {
          type: 0,
          isDeleted: false,
          state: 0
        },
        {
          type: 1,
          isDeleted: false,
          state: 0
        },
        {
          type: 0,
          isDeleted: false,
          state: 0
        },
        {
          type: 1,
          isDeleted: false,
          state: 0
        }
      ]
    };
  }
};
</script>

<style lang="less" scoped>
#msg {
  height: 100%;
  display: flex;
  flex-direction: column;
  .top {
    width: 100%;
    text-indent: 20px;
    color: #00a464;
    font-size: 14px;
    font-weight: 600;
    height: 32px;
    line-height: 32px;
    border-bottom: 1px solid #e0e0e0;
  }
  .contain {
    flex-grow: 1;
    background-color: #f4fbf8;
    overflow-y: scroll;
    padding: 0 20px;
    .item {
      display: flex;
      align-items: center;
      .info-left {
        flex-grow: 1;
        padding-right: 20px;
        &-top {
          height: 40px;
          display: flex;
          align-items: center;
          .time {
            font-size: 12px;
            color: #b4b7b5;
          }
          .icon {
            width: 16px;
            height: 16px;
            margin: 0 5px;
            img {
              height: 100%;
              width: 100%;
            }
          }
        }
        .text-line {
          display: flex;
          .text {
            width: 220px;
            font-size: 12px;
            background-color: #ccede0;
            line-height: 20px;
            padding: 10px;
            border-radius: 10px;
          }
        }
      }
      .info-right {
        width: 14px;
        padding-top: 40px;
      }
    }
    .isRight {
      .info-left {
        &-top {
          flex-direction: row-reverse;
        }
        .text-line {
          flex-direction: row-reverse;
          .text {
            background-color: #00a464;
          }
        }
      }
    }
  }
}
</style>