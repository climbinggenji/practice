<template>
    <div id="content">
        <WhatsApp></WhatsApp>
    </div>
</template>

<script>
import WhatsApp from "./contents/WhatsApp.vue";
export default {
  components: {
    WhatsApp
  }
};
</script>

<style lang="less" scoped>
#content {
  width: 835px;
  height: 100%;
}
</style>