<template>
  <view>
    <view style="height: 104upx"></view>
    <view class="cu-bar foot padding-left-sm padding-right-sm padding-top-sm padding-bottom-sm bg-white">
      <button class="cu-btn response" :class="[bgColor]" @click="handleSave" :disabled="disabled">
        <text class="cuIcon-loading2 cuIconfont-spin margin-right-xs" v-if="loading"></text>
        {{ title }}
      </button>
    </view>
  </view>
</template>

<script>
export default {
  props: {
    loading: {
      type: Boolean,
      default: false
    },
    title: {
      type: String,
      default: '保存'
    },
    bgColor: {
      type: String,
      default: 'bg-blue'
    },
    disabled: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    handleSave() {
      if (this.loading) {
        return;
      }
      this.$emit('save');
    }
  }
};
</script>

<style scoped lang="scss">
.foot {
  z-index: 10;
}
</style>
