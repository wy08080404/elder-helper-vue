<template>
  <view>
    <view class="user-container">
      <view class="user-left">
        <image class="portrait" src="../../static/elderUser.jpg"></image>
      </view>
      <view class="user-right">
        <text class="name">{{ name }}</text>
        <text class="age">{{ age }}</text>
      </view>
    </view>

    <view class="button-container">
      <view class="exit-button" @click="showConfirmationDialog = true" :class="{ 'hovered': isHovered }" @mouseover="isHovered = true" @mouseout="isHovered = false">
        <text class="button-text">退出</text>
      </view>
    </view>

    <!-- Popup Dialog -->
    <view v-if="showConfirmationDialog" class="popup-dialog">
      <text class="dialog-text">是否确定退出？</text>
      <view class="dialog-button-container">
        <view class="dialog-button" @click="exit">确定</view>
        <view class="dialog-button" @click="showConfirmationDialog = false">取消</view>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      name: "loopy(老年版)",
      age: "年龄：99",
      isHovered: false,
      showConfirmationDialog: false,
    };
  },
  methods: {
    exit() {
      // Add your exit logic here
      console.log("Exit button clicked");
    },
  },
};
</script>

<style lang="scss">
.user-container {
  display: flex;
  flex-direction: row;
  justify-content: center;
  background-color: #ffffff;
}

.user-left {
  margin-left: 80rpx;
  margin-top: 40rpx;
  margin-right: 30rpx;
  width: 100rpx; /* 左侧容器的宽度 */
}

.portrait {
  width: 130rpx; /* 图片的宽度 */
  height: 130rpx; /* 图片的高度 */
  border: 1rpx solid white;
  border-radius: 10%;
}

.user-right {
  margin-left: 70rpx;
  margin-top: 35rpx;
  flex: 1;
  padding-left: 10rpx; /* 右侧容器的左边距，可根据需求调整 */
  display: flex;
  flex-direction: column;
}

.name {
  margin-top: 10rpx;
  font-size: 40rpx; /* 第一行文字的字号，可根据需求调整 */
  font-weight: bold;
}

.age {
  font-size: 30rpx; /* 第二行文字的字号，可根据需求调整 */
  margin-top: 20rpx; /* 第二行文字与第一行文字的间距，可根据需求调整 */
}

.button-container {
  position: fixed;
  bottom: 0;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 20px;
}

.exit-button {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 150px; /* 修改宽度 */
  height: 150px; /* 修改高度 */
  background-color: #ccc;
  border-radius: 10px;
  cursor: pointer;
  transition: all 0.3s ease;
}

.exit-button.hovered {
  transform: scale(1.1);
}

.button-text {
  font-size: 30px;
  font-weight: bold;
}

.popup-dialog {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  z-index: 999;
}

.dialog-text {
  font-size: 24px;
  font-weight: bold;
  color: white;
  margin-bottom: 20px;
}

.dialog-button-container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.dialog-button {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 120px;
  height: 120px;
  background-color: #ccc;
  border-radius: 5px;
  margin: 10px;
  cursor: pointer;
  font-size: 18px;
  font-weight: bold;
}
</style>