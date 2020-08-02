<template>
  <div id="home-nav">
    <div class="nav-logo">
      <span class="nav-logo-text">米</span>
      <span class="iconfont icondaohangshouye"></span>
    </div>

    <div class="doodle">
      <a href="#">
        <img src="~assets/img/home/doodle.gif" alt="" />
      </a>
    </div>

    <div class="nav-right">
      <ul class="nav-list">
        <li><span>小米手机</span></li>
        <li><span>Redmi 红米</span></li>
        <li><span>电视</span></li>
        <li><span>笔记本</span></li>
        <li><span>家电</span></li>
        <li><span>路由器</span></li>
        <li><span>智能硬件</span></li>
        <li><span>服务</span></li>
        <li><span>社区</span></li>
      </ul>
      <div class="search">
        <input type="text" placeholder="搜索点什么哟" />
        <div class="btn">
          <span class="iconfont iconsearch"></span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "NavBar",
};
</script>

<style scoped>
#home-nav {
  display: flex;
  width: 1226px;
  margin: auto;
  margin-top: 20px;
}
.nav-logo {
  background-color: #ff6700;
  width: 55px;
  height: 55px;
  position: relative;
  color: #ffff;
  text-align: center;
  line-height: 55px;
  overflow: hidden;
  cursor: pointer;
  margin-right: 15px;
}
.nav-logo .nav-logo-text {
  color: #ffffff;
  font-size: 30px;
  position: relative;
  transition: all 0.1s;
  left: 0px;
}
.nav-logo:hover .nav-logo-text {
  left: 60px;
}

.nav-logo .icondaohangshouye {
  /* color: #ffffff; */
  color: #ffffff;
  position: relative;
  font-size: 30px;
  transition: all 0.1s;
  left: -50px;
  top: -60px;
}

.nav-logo:hover .icondaohangshouye {
  left: 0;
}

.nav-right {
  display: flex;
  position: relative;
  justify-content: space-between;
}

.nav-list {
  display: flex;
  flex: 1;
}

.nav-list li {
  padding: 26px 10px 38px 10px;
}
.nav-list li span {
  cursor: pointer;
}
.nav-list li span:hover {
  color: #ff6700;
}

.nav-right .search {
  position: relative;
  right: 0;
  display: flex;
  left: 78px;
  top: 10px;
}

.nav-right .search input {
  width: 244px;
  height: 48px;
  border: 1px solid #cccccc;
  outline: none;
  padding: 0px 10px;
}
.nav-right .search .btn {
  width: 38px;
  height: 46px;
  border: 1px solid #cccccc;
  border-left: none;
  padding: 0px 6px 0px 6px;
  text-align: center;
  line-height: 49px;
  box-sizing: content-box;
  font-weight: 800;
  transition: 0.2s;
}
.nav-right .search .btn:hover {
  background-color: #ff6700;
  color: #ffffff;
}
</style>
