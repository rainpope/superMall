<template>
  <div id="swiper-nav">
    <ul>
      <li><span>手机 电话卡</span><span>&gt;</span></li>
      <li><span>电视 盒子</span><span>&gt;</span></li>
      <li><span>笔记本显示器</span><span>&gt;</span></li>
      <li><span>家电 插线板</span><span>&gt;</span></li>
      <li><span>出行 穿戴</span><span>&gt;</span></li>
      <li><span>智能 路由器</span><span>&gt;</span></li>
      <li><span>电源 配件</span><span>&gt;</span></li>
      <li><span>健康 儿童</span><span>&gt;</span></li>
      <li><span>耳机 音箱</span><span>&gt;</span></li>
      <li><span>生活 箱包</span><span>&gt;</span></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "SwiperNav",
  props: {
    swiper: {
      type: {},
    },
  },
};
</script>

<style scoped>
#swiper-nav {
  width: 234px;
  height: 460px;
  position: absolute;
  background-color: rgba(00, 00, 00, 0.3);
  left: 0;
  top: 0;
  color: #ffffff;
  padding: 20px 0;
}

#swiper-nav ul {
  line-height: 42px;
  color: #eeeeee;
}
#swiper-nav ul li {
  width: 100%;
  height: 42px;
  padding-left: 30px;
}
#swiper-nav ul li:hover {
  background-color: #ff6700;
}
#swiper-nav li span:nth-child(2) {
  float: right;
  padding-right: 20px;
  font-weight: 1000;
  font-size: 18px;
}
</style>
