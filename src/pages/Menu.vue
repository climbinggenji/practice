<template>
  <div id="menu">
      <div v-for="(item, index) in menuList" :key="index" class="item" :class="{isSelect: item.isSelect}">
          <div class="left">
              <div class="icon">
                  <img v-if="item.isSelect" :src="item.selectIcon">
                  <img v-else :src="item.icon">
              </div>
              <div class="name" @click="change(item)">{{item.name}}</div>
              <div class="tag">({{item.tag}})</div>
          </div>
          <div class="right">
              <CheckBox :state.sync="item.state" :focus="item.isSelect"></CheckBox>
          </div>
      </div>
    </div>
</template>

<script>
import CheckBox from "./components/CheckBox.vue";

export default {
  name: "Menu",
  components: {
    CheckBox
  },
  data() {
    return {
      menuList: [
        {
          id: 0,
          name: "Contacts",
          tag: 37,
          state: 0, // 选框状态，0未选 1+ 2-
          isSelect: false
        },
        {
          id: 1,
          name: "Messages",
          tag: 9,
          state: 0,
          isSelect: false
        },
        {
          id: 2,
          name: "Call History",
          tag: 36,
          state: 0,
          isSelect: false
        },
        {
          id: 3,
          name: "WhatsApp",
          tag: 0,
          state: 0,
          isSelect: true
        },
        {
          id: 4,
          name: "WhatsApp Attach",
          tag: 0,
          state: 0,
          isSelect: false
        },
        {
          id: 5,
          name: "Gallery",
          tag: 2123,
          state: 0,
          isSelect: false
        },
        {
          id: 6,
          name: "Documents",
          tag: 337,
          state: 0,
          isSelect: false
        },
        {
          id: 7,
          name: "Videos",
          tag: 28,
          state: 0,
          isSelect: false
        },
        {
          id: 8,
          name: "Audio",
          tag: 37,
          state: 0,
          isSelect: false
        }
      ]
    };
  },
  created() {
    this.menuList.forEach(element => {
      let name = element.name
        .toLowerCase()
        .split(" ")
        .join("_");
      element.icon = require(`@/assets/dback/${name}24x24.png`);
      element.selectIcon = require(`@/assets/dback/${name}_select24x24.png`);
    });
  },
  methods: {
    change(item) {
      // 菜单选中切换
      if (item.isSelect) {
        return;
      } else {
        this.menuList.forEach(element => {
          element.isSelect = false;
        });
        item.isSelect = true;
      }
    }
  }
};
</script>

<style lang="less" scoped>
#menu {
  width: 215px;
  .item {
    display: flex;
    width: 215px;
    justify-content: space-between;
    padding: 0 20px 0 25px;
    border-right: 1px solid #e0e0e0;
    color: #333333;
    &:hover {
      background-color: antiquewhite;
    }

    .left {
      height: 60px;
      .icon {
        height: 24px;
        width: 24px;
      }
      .name {
        max-width: 95px;
        font-size: 12px;
        text-indent: 10px;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
        &:hover {
          text-decoration-line: underline;
          cursor: pointer;
        }
      }
      .tag {
        font-size: 12px;
        text-indent: 5px;
      }
      display: flex;
      flex-wrap: nowrap;
      align-items: center;
    }
    .right {
      line-height: 60px;
      img {
        cursor: pointer;
      }
    }
  }
  .isSelect {
    color: #01a465;
    background-color: #ccede0;
    &:hover {
      background-color: #ccede0;
    }
  }
}
</style>