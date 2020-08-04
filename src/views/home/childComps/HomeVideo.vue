<template>
  <div class="home-video">
    <div class="home-video-hd">
      <h2 class="title">视频</h2>

      <div class="more">
        <a href="">
          查看全部
          <span class="iconfont iconright_6"></span>
        </a>
      </div>
    </div>

    <div class="home-video-bd">
      <ul>
        <li v-for="item in homeVideo">
          <a :href="item.url">
            <div class="img-box">
              <img :src="item.img" :alt="item.title" />
              <div class="play">
                <span class="iconfont iconicon_play"></span>
              </div>
            </div>
            <h3>{{ item.title }}</h3>
            <p v-if="item.desc != null">{{ item.desc }}</p>
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomeVideo",
  props: {
    homeVideo: {
      type: Array,
    },
  },
};
</script>

<style scoped>
.home-video {
  width: 1226px;
  margin: auto;
}
/* 头部CSS */
.home-video-hd {
  width: 100%;
  height: 58px;
  line-height: 58px;
}
.home-video-hd .title {
  font-weight: 200;
  font-size: 22px;
  color: #333;
  float: left;
}
.home-video-hd .more {
  float: right;
}
.home-video-hd .more a {
  color: #333;
  transition: 0.3s;
}
.home-video-hd .more:hover a,
.home-video-hd .more:hover span {
  color: #ff6700;
}
.home-video-hd span {
  margin-left: 5px;
  font-size: 22px;
  color: #b0b0b0;
  position: relative;
  top: 2px;
  transition: 0.3s;
}

/* 中间的css样式 */
.home-video-bd ul {
  width: 100%;
  display: flex;
  justify-content: space-between;
}

.home-video-bd li {
  width: 296px;
  height: 285px;
  background-color: #ffffff;
  text-align: center;
  position: relative;
  top: 0;
  transition: 0.5s;
}
.home-video-bd li:hover {
  top: -3px;
  box-shadow: 1px 1px 15px #c0c0c0;
}
.home-video-bd li img {
  width: 100%;
  margin-bottom: 33px;
}
.home-video-bd li h3 {
  margin: 0 14px 6px;
  font-size: 14px;
  font-weight: 400;
  text-align: center;
  color: #333;
  white-space: nowrap;
  text-overflow: ellipsis;
  overflow: hidden;
}
.home-video-bd li p {
  height: 18px;
  margin: 0 14px;
  font-size: 12px;
  color: #b0b0b0;
  white-space: nowrap;
  text-overflow: ellipsis;
  overflow: hidden;
}

/* 播放按钮的css */
.img-box {
  position: relative;
}
.play {
  width: 40px;
  height: 25px;
  border-radius: 35%;
  border: 2px solid #fff;
  color: #fff;
  position: absolute;
  text-align: center;
  bottom: 10px;
  left: 20px;
  z-index: 1;
  line-height: 20px;
  transition: 0.3s;
}
.home-video-bd li:hover .play {
  background-color: #ff6700;
  border-color: #ff6700;
}
</style>
