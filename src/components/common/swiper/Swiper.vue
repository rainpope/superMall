<template>
  <div id="swiper" @mouseenter="cleartimer" @mouseleave="settimer">
    <div class="image" ref="image">
      <img
        :src="item.url"
        alt="item.url"
        v-for="item in swiperUrls"
        class="img-item"
      />
    </div>
    <div class="go-left" @click="prePic">
      <span>&lt;</span>
    </div>
    <div class="go-right" @click="nextPic">
      <span>&gt;</span>
    </div>
    <ul class="swiper-btns">
      <li
        class="btn"
        v-for="(item, index) in swiperUrls"
        :class="{ active: index == curIndex }"
        @click="btnClick(index)"
      ></li>
    </ul>
    <swiper-nav></swiper-nav>>
  </div>
</template>

<script>
import SwiperNav from "./SwiperNav";
export default {
  name: "SwiperItem",
  props: {
    swiperUrls: {
      type: Array,
    },
  },
  components: {
    SwiperNav,
  },
  data() {
    return {
      curIndex: 0,
      imgsLength: 0,
      imgBox: null,
      imgs: [],
      timer: null,
    };
  },
  mounted() {
    this.imgBox = document.getElementsByClassName("image")[0];
    this.imgs = document.getElementsByClassName("img-item");
    this.imgsLength = this.imgs.length;

    this.timer = setInterval(() => {
      this.nextPic();
    }, 3000);
  },
  methods: {
    prePic() {
      // 图片下标减1，如何下标大于图标的数量让下标等于0重新循环
      this.curIndex--;
      if (this.curIndex < 0) {
        this.curIndex = this.imgsLength - 1;
      }
      this.picMove();
    },
    nextPic() {
      // 图片下标加1，如何下标大于图标的数量让下标等于0重新循环
      this.curIndex++;
      if (this.curIndex >= this.imgsLength) {
        this.curIndex = 0;
      }
      // 图片移动
      this.picMove();
    },
    picMove() {
      //遍历所有图片，让下标等于当前图片的显示，不等于的消失
      for (let i = 0; i < this.imgsLength; i++) {
        if (i === this.curIndex) {
          this.imgs[i].style.display = "block";
          // this.imgs[i].style.animation = "fadeOut 2s";
        } else {
          // this.imgs[i].style.animation = "fadeOut 2s";
          this.imgs[i].style.display = "none";
        }
      }
    },
    cleartimer() {
      // 鼠标移入取消定时器
      clearInterval(this.timer);
    },
    settimer() {
      // 鼠标移出设置定时器
      this.timer = setInterval(() => {
        this.nextPic();
      }, 3000);
    },
    btnClick(index) {
      this.curIndex = index;
      this.picMove();
    },
  },
};
</script>

<style scoped>
#swiper {
  position: relative;
  width: 1226px;
  height: 460px;
  margin: auto;
  cursor: pointer;
}

.image {
  position: relative;
  width: 100%;
}
.image img {
  width: 100%;
  position: absolute;
  left: 0;
  top: 0;
  display: none;
  /* opacity: 0; */
}
.image img:nth-child(1) {
  display: block;
  opacity: 1;
}

.go-left,
.go-right {
  position: absolute;
  width: 41px;
  height: 69px;
  line-height: 69px;
  font-size: 40px;
  text-align: center;
  color: #aaaaaa;
  z-index: 1;
}
.go-left:hover,
.go-right:hover {
  background-color: rgba(00, 00, 00, 0.5);
}
.go-left {
  top: calc(50% - 35px);
  left: 234px;
}
.go-right {
  right: 0;
  top: calc(50% - 35px);
}

.swiper-btns {
  position: absolute;
  display: flex;
  z-index: 9;
  bottom: 30px;
  right: 30px;
}
.btn {
  width: 10px;
  height: 10px;
  background-color: #777777;
  border: 2px solid #aaaaaa;
  border-radius: 50%;
  margin-left: 5px;
}

.active {
  background-color: #fffeee;
}
.fadeOut {
  animation: fadeOut 1s;
}
.fadeIn {
  animation: fadeIn 1s;
}
/* 动画效果 */
@keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-webkit-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
/*淡入*/
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>
