<template>
  <view>
    <view class="content">
      <image class="banner" src="../../static/images/testImg.png" mode=""></image>
      <view class="modelTitle">预约报名</view>
      <view class="form">
        <view title="" note="" class="item">
          <view class="itemName">
            单位所在地
            <text>*</text>
          </view>
          <picker @change="selCity" @columnchange="selMonitor" :value="addressIndex" :range="address" mode="multiSelector">
            <view class="setCon">
              <input type="text" :value="addressNode.province + addressNode.city" disabled="" />
              <icon class="iconfont iconkefu"></icon>
            </view>
          </picker>
        </view>
      </view>
      <view class="sub"><view>确定</view></view>
    </view>
    <view class="company">陕西秦盾爆破技术培训中心有限公司</view>
  </view>
</template>

<script>
import address from '../../static/json/address.json';
// console.log(address)
export default {
  data() {
    return {
      address: [],
      provinceList: [],
      cityAllList: [],
      addressIndex: [0, 0],
      addressNode: {
        province: "请选择城市",
        city: ""
      }
    };
  },
  onLoad() {
    const that = this
    // 将省市区的数据转换为picker可用的多维数组
    that.getAddressData()
  },
  methods: {
    // 获取地址信息
    selCity(e) {
      const that = this;
      let val = e.target.value
      that.addressNode = {
        province: that.address[0][val[0]],
        city: that.address[1][val[1]]
      }
    },
    // 监听省市区滚动
    selMonitor(e) {
      const that = this
      let column = e.detail.column
      if (column == 0) {
        let index = e.detail.value
        that.address[1] = that.cityAllList[index]
      }
    },
    // 将省市区的数据转换为picker可用的多维数组
    getAddressData() {
      const that = this;
      // 所有城市列表,二维数组
      let cityAllList = [];
      // 省列表
      let provinceList = [];
      // address为省市区的json数据
      for (let key in address) {
        let newDataList = [];
        if (address[key].children) {
          for (let key2 in address[key].children) {
            newDataList.push(address[key].children[key2].name);
          }
        }
        provinceList.push(address[key].name);
        cityAllList.push(newDataList);
      }
      that.provinceList = provinceList;
      that.cityAllList = cityAllList;
      that.address = [provinceList, cityAllList[0]];
    }
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
  .banner {
    width: 100%;
    height: 230rpx;
  }
  .modelTitle {
    font-size: 54rpx;
    color: $mainFontColor;
    padding: 30rpx 0 30rpx 30rpx;
    border-bottom: 1rpx solid $borderColor;
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
        text {
          color: red;
          padding: 10rpx;
        }
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
          padding-right: 20rpx;
        }
      }
    }
  }
  .sub {
    position: absolute;
    width: 100%;
    bottom: 0;
    left: 0;
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
