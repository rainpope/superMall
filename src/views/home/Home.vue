<template>
  <div id="home">
    <swiper :swiperUrls="swiperUrls"> </swiper>
  </div>
</template>

<script>
import Swiper from "components/common/swiper/Swiper";
import SwiperItem from "components/common/swiper/SwiperItem";
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
  },
  methods: {},
};
</script>

<style scoped></style>
