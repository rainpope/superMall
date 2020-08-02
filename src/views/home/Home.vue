<template>
  <div id="home">
    <swiper :swiperUrls="swiperUrls"> </swiper>
    <home-hero></home-hero>
    <div class="home-bg">
      <flash-sale></flash-sale>
      <home-banner>
        <a href="#">
          <img
            src="//cdn.cnbj1.fds.api.mi-img.com/mi-mall/e9f7817b9a66ef21d196f6ae6ee6efd7.jpg?thumb=1&w=1226&h=120&f=webp&q=90"
            alt=""
          />
        </a>
      </home-banner>
    </div>
  </div>
</template>

<script>
import Swiper from "components/common/swiper/Swiper";
import SwiperItem from "components/common/swiper/SwiperItem";

import HomeHero from "./childComps/HomeHero";
import FlashSale from "./childComps/FlashSale";
import HomeBanner from "./childComps/HomeBanner";

export default {
  name: "Home",
  data() {
    return {
      swiperUrls: [
        {
          url:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/66c6d0c733c9b8a2dca728033adedc0b.jpg?w=2452&h=920",
        },
        {
          url:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/cc880682e314092bd56a4c2d6b044e83.jpg?thumb=1&w=1226&h=460&f=webp&q=90",
        },
        {
          url:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/ac3ef452ba1527d6bf32dc2c3ffc617c.jpg?thumb=1&w=1226&h=460&f=webp&q=90",
        },
        {
          url:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/38027051c90bab4b597f46a2375cbbe0.jpg?thumb=1&w=1226&h=460&f=webp&q=90",
        },
        {
          url:
            "https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/c1a9b2f68ac5219ecbaa5538f24f6220.jpg?thumb=1&w=1226&h=460&f=webp&q=90",
        },
      ],
    };
  },
  components: {
    Swiper,
    SwiperItem,
    HomeHero,
    FlashSale,
    HomeBanner,
  },
  methods: {},
};
</script>

<style scoped>
.home-bg {
  background-color: #f5f5f5;
}
</style>
