<template>
  <div id="top-bar">
    <div class="top-bar-content">
      <div class="left">
        <div>小米商城</div>
        <span>丨</span>
        <div>MIUI</div>
        <span>丨</span>
        <div>loT</div>
        <span>丨</span>
        <div>云服务</div>
        <span>丨</span>
        <div>金融</div>
        <span>丨</span>
        <div>有品</div>
      </div>
      <div class="right">
        <div>登录</div>
        <span>丨</span>
        <div>注册</div>
        <div class="top-bar-cart">
          <span class="iconfont iconicon-"></span>
          <span class="top-bar-cart-text"> 购物车(0)</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TopBar",
};
</script>

<style scoped>
#top-bar {
  width: 100%;
  background-color: #333333;
  color: #cccccc;
  line-height: 40px;
  font-size: 13px;
}
.top-bar-content {
  width: 1226px;
  display: flex;
  margin: auto;
  height: 40px;
}
.left {
  display: flex;
  flex: 1;
}
.left div,
.right div {
  cursor: pointer;
}
.left div:hover,
.right div:hover {
  color: #ffffff;
}
.left span {
  color: rgba(77, 77, 77, 1);
}
.right {
  display: flex;
}
.right .top-bar-cart {
  width: 120px;
  text-align: center;
  background-color: #424242;
  margin-left: 10px;
  position: relative;
  margin-right: none;
}
.top-bar-content .top-bar-cart:hover {
  background-color: #ffffff;
  color: orange;
}
.top-bar-cart .iconicon- {
  margin-right: 5px;
  font-size: 25px;
}
.top-bar-cart-text {
  position: relative;
  top: -4px;
}
</style>
