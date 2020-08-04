<template>
  <div class="tool-bar">
    <div class="tool">
      <a href="" class="btn">
        <span class="tool-icon iconfont iconshouji"></span>
        <span class="tool-text">手机APP</span>
      </a>
      <a href="" class="btn">
        <span class="tool-icon iconfont iconwode2"></span>
        <span class="tool-text">个人中心</span>
      </a>
      <a href="" class="btn">
        <span class="tool-icon iconfont iconbanshou"></span>
        <span class="tool-text">售后服务</span>
      </a>
      <a href="" class="btn">
        <span class="tool-icon iconfont iconkefu"></span>
        <span class="tool-text">人工客服</span>
      </a>
      <a href="" class="btn">
        <span class="tool-icon iconfont iconicon-"></span>
        <span class="tool-text">购物车</span></a>
      <a href="" class="to-top btn">
          <span class="tool-icon iconfont iconfanhuidingbu"></span>
          <span class="tool-text">回顶部</span></a>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: "ToolBar",
}
</script>

<style>
  @media all and (max-width: 1457px) {
    .tool-bar {
      left: 50%;
      right: auto;
      margin-left: 621px;
      bottom: 40px;
    }
    .tool-bar .tool .btn {
      position: relative;
      width: 25px;
      height: 40px;
    }
    .tool-text {
      position: absolute;
      display: none;
      
      width: 74px;
      height: 30px;
      font-size: 14px;
      left: -80px;
      top: -42px;
      background-color: #fff;
      border: 1px solid #eeeeee;
      line-height: 30px;
      color: #757575;
    }
    .tool-bar .tool .btn:hover .tool-text{
      color: #757575;
      display: block;
    }
    .tool-bar .btn .tool-icon {
      position: relative;
      font-size: 17px;
      width: 100%;
      height: 100%;
      top: -5px;
    }
    @media all and (max-width: 1310px) {
      .tool-bar .tool {
        position: fixed;
        right: 0;
        bottom: 40px;
        z-index: 99;
      }
    }
  }
.tool-bar {
  position: fixed;
  right: 0;
  bottom: 70px;
  z-index: 99;
}
/* tool-bar样式 */
.tool .btn {
  position: relative;
  display: block;
  width: 82px;
  height: 90px;
  margin-top: -1px;
  background-color: #fff;
  border: 1px solid #f5f5f5;
  text-align: center;
  color: #757575;
  transition: 0.3s;
}
.tool .btn:hover{
  color: #F87300;
}
.tool .tool-icon {
  display: block;
  font-size: 30px;
  position: relative;
  width: 30px;
  height: 30px;
  margin: 0 auto 8px;
  padding-top: 18px;
}
.tool .tool-text{
  position: relative;
  text-align: center;
  bottom: -20px;
}
.tool .to-top {
  margin-top: 20px;
}

</style>