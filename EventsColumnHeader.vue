<template>
  <view class="container">
    <view class="left">
      <text class="month-heading">September</text>
    </view>
    <view class="right">
      <view class="badge">
        <text class="badge-text">1</text>
    </view>
  </view>
</template>
<style>
.container {
  padding-top: 20;
  height: 100;
  border-bottom-width: 0.5;
  border-bottom-color: #ddd;
  flex-direction: row;
}

.left {
  flex: 5;
  height: 100;
  justify-content: center;
  align-items: center;
}
.right {
  flex: 2;
  height: 100;
  justify-content: center;
  align-items: center;
}

.badge {
  padding: 5;
  background-color: #f44;
  color: white;
  width: 30;
  height: 30;
  text-align: center;
  border-radius: 40;
  border-width: 2;
  border-color: white;
  shadow-color: red;
  shadow-opacity: 0.2;
}

.badge-text {
  color: white;
  text-align: center;
  font-weight: bold;
}

.month-heading {
  color: #666;
}
</style>