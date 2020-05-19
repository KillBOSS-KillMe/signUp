<template>
  <view>
    <scroll-view scroll-y="true" class="content">
      <view class="explanation">
        <view class="modelTitle">西安市培训人数统计表</view>
        <text>填写注意事项如下：</text>
        <text>1、请如实无误填写以下信息表；</text>
        <text>2、培训人数将以最新数据为准；</text>
        <text>3、具体报名流程请至参训指南。</text>
      </view>
     <view class="form">
        <view class="item">
          <view class="itemName">
            单位名称
            <text>*</text>
          </view>
          <text class="description">（请填写作业证内的单位名称，如有作业点或者项目部请备注。）</text>
          <view class="setCon">
            <icon class="iconfont iconkefu"></icon>
            <input type="text" value="" />
          </view>
        </view>
        <view class="item">
          <view class="itemName">
            领队姓名
            <text>*</text>
          </view>
          <view class="setCon">
            <icon class="iconfont iconkefu"></icon>
            <input type="text" value="" />
          </view>
        </view>
        <view class="item">
          <view class="itemName">
            电话号码
            <text>*</text>
          </view>
          <view class="setCon">
            <icon class="iconfont iconkefu"></icon>
            <input type="text" value="" />
          </view>
        </view>
        <view class="item">
          <view class="itemName">
            邮箱
            <text>*</text>
          </view>
          <view class="setCon">
            <icon class="iconfont iconkefu"></icon>
            <input type="text" value="" />
          </view>
        </view>
        <view class="item">
          <view class="itemName">
            三大员首次培训人数统计（请输入不小于0的数字）
            <text>*</text>
          </view>
          <view class="setCon">
            <icon class="iconfont iconkefu"></icon>
            <input type="text" value="" />
          </view>
        </view>
        <view class="item">
          <view class="itemName">
            三大员继续教育培训人数统计（请输入不小于0的数字）
            <text>*</text>
          </view>
          <view class="setCon">
            <icon class="iconfont iconkefu"></icon>
            <input type="text" value="" />
          </view>
        </view>
        <view class="item">
          <view class="itemName">
            初级/D人数
          </view>
          <view class="setCon">
            <icon class="iconfont iconkefu"></icon>
            <input type="text" value="" />
          </view>
        </view>
        <view class="item">
          <view class="itemName">
            高级/A人数
          </view>
          <view class="setCon">
            <icon class="iconfont iconkefu"></icon>
            <input type="text" value="" />
          </view>
        </view>
        <view class="item">
          <view class="itemName">
            工程技术人员继续教育人数统计（请输入不小于0的数字）
            <text>*</text>
          </view>
          <view class="setCon">
            <icon class="iconfont iconkefu"></icon>
            <input type="text" value="" />
          </view>
        </view>
        <view class="item">
          <view class="itemName">
            您想参加此次培训的时间为？
            <text>*</text>
          </view>
          <view class="setCon">
            <icon class="iconfont iconkefu"></icon>
            <input type="text" value="" />
          </view>
        </view>
      </view>
      <view class="sub">
        <view>确定</view>
      </view>
    </scroll-view>
    <view class="company">陕西秦盾爆破技术培训中心有限公司</view>
  </view>
</template>

<script>
export default {
  data() {
    return {};
  }
};
</script>

<style lang="scss">
page {
  width: 100vw;
  height: 100vh;
}
.content {
  width: calc(100vw - 60rpx);
  height: calc(100vh - 120rpx);
  position: relative;
  margin: 30rpx;
  background-color: #fff;
  .explanation {
    width: 100%;
    height: auto;
    padding: 30rpx;
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    flex-direction: column;
    border-bottom: 1rpx solid $borderColor;
    .modelTitle {
      font-size: 54rpx;
      color: $mainFontColor;
      padding-bottom: 15rpx;
    }
    text {
      padding: 15rpx;
    }
  }

  .form {
    width: 630rpx;
    height: auto;
    padding: 30rpx;
    .item {
      width: 650rpx;
      height: auto;
      
      .itemName {
        font-size: $titleSize_1;
        font-weight: $mainFontWeight;
        color: $mainFontColor;
        padding-top: 40rpx;
        text {
          color: red;
          padding: 10rpx;
        }
      }
      .description {
        width: 100%;
        font-size: $descriptionSize;
        color: $fontColor_2;
        padding-top: 20rpx;
      }
      .setCon {
        width: 610rpx;
        height: 30rpx;
        padding: 19rpx;
        margin: 20rpx 0;
        border: 1rpx solid $borderColor;
        display: flex;
        align-items: center;
        justify-content: space-between;
        input {
          width: 100%;
          padding-left: 20rpx;
        }
      }
    }
  }
  .sub {
    width: 100%;
    border-top: 1rpx solid $borderColor;
    padding: 50rpx 0;
    display: flex;
    align-items: center;
    justify-content: center;
    view {
      width: 630rpx;
      height: 80rpx;
      display: flex;
      align-items: center;
      justify-content: center;
      background-color: $themeColor;
      font-size: $titleSize_1;
      color: #fff;
    }
  }
}
.company {
  width: 100%;
  height: auto;
  padding-bottom: 30rpx;
  font-size: $titleSize_1;
  color: $fontColor_2;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
