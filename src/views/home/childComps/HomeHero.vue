<template>
  <div id="home-hero">
    <div class="hero-contnet">
      <ul>
        <li>
          <span class="hero-li-icon iconfont icontime"></span>
          <span class="hero-li-text">小米秒杀</span>
        </li>
        <li>
          <span class="hero-li-icon iconfont iconqiye"></span>
          <span class="hero-li-text">企业团购</span>
        </li>
        <li>
          <span class="hero-li-icon iconfont iconshouji"></span>
          <span class="hero-li-text">F码通道</span>
        </li>
        <li>
          <span class="hero-li-icon iconfont iconneicunka"></span>
          <span class="hero-li-text">米粉卡</span>
        </li>
        <li>
          <span class="hero-li-icon iconfont iconqian"></span>
          <span class="hero-li-text">以旧换新</span>
        </li>
        <li>
          <span class="hero-li-icon iconfont iconhuafei"></span>
          <span class="hero-li-text">话费充值</span>
        </li>
      </ul>
    </div>

    <div class="hero-img">
      <ul>
        <li v-for="item in heroImgs">
          <img :src="item.url" alt="" />
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomeHero",
  data() {
    return {
      heroImgs: [
        {
          url:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/c0c05274f2fbb55fbccb89622f798907.jpg?w=632&h=340",
        },

        {
          url:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/b746a4db2e0473cc076a3a4b9bbe0235.jpg?w=632&h=340",
        },
        {
          url:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/816a66edef10673b4768128b41804cae.jpg?w=632&h=340",
        },
      ],
    };
  },
};
</script>

<style scoped>
#home-hero {
  width: 1226px;
  height: 170px;
  margin: 14px auto 26px;
}
.hero-contnet {
  color: #ffffff;
  float: left;
}

.hero-contnet ul {
  padding: 3px;
  width: 233.5px;
  height: 170px;
  /* margin-left: 6px; */
  background-color: #5f5750;
  display: grid;
  grid-template-columns: 77.8px 77.8px 77.8px;
  grid-template-rows: 82px 82px 82px;
  position: relative;
}
.hero-contnet ul li {
  text-align: center;
  padding-top: 18px;
  position: relative;
}
.hero-contnet ul li::before,
.hero-contnet ul li::after {
  position: absolute;
  content: "";
  background: #665e57;
}
.hero-contnet ul li::before{
  top: 2px;
  left: 6px;
  width: 64px;
  height: 1px;
}
.hero-contnet ul li::after {
  top: 6px;
  left: 0;
  width: 1px;
  height: 70px;
}
.hero-contnet ul span {
  display: block;
  color: #bbbbbb;
  transition: 0.2s;
  cursor: pointer;
}
.hero-contnet li:hover span {
  color: #ffffff;
}
.hero-contnet ul .hero-li-icon {
  font-size: 25px;
  margin-bottom: 5px;
}
.hero-contnet ul .hero-li-text {
  font-size: 12px;
}

.hero-img {
  float: left;
}
.hero-img ul {
  display: table;
}

.hero-img li {
  width: 316px;
  height: 170px;
  float: left;
  display: list-item;
  margin-left: 14.5px;
}
.hero-img img {
  width: 100%;
  cursor: pointer;
}
</style>
