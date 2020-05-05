<template>
    <div>
        <input type="text" placeholder="Search" id="search">
    </div>
</template>

<script>
export default {
  name: "Input"
};
</script>

<style lang="less" scoped>
#search {
  width: 170px;
  height: 28px;
  border-radius: 5px;
  border: 1px solid #14ac72;
  background: rgba(255, 255, 255, 0.5);
  text-indent: 30px;
  color: #14ac72;
  &:-moz-placeholder {
    color: #14ac72;
  }
  &:-ms-input-placeholder {
    color: #14ac72;
  }
  &::-moz-placeholder {
    color: #14ac72;
  }
  &::-webkit-input-placeholder {
    color: #14ac72;
  }
}
</style>