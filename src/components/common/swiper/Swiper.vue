<template>
  <div id="swiper">
    <div class="image" ref="image">
      <img
        :src="item.url"
        alt="item.url"
        v-for="item in swiperUrls"
        class="img-item"
      />
    </div>
    <div class="go-left" @click="goLeft">
      <span>&lt;</span>
    </div>
    <div class="go-right" @click="goRight">
      <span>&gt;</span>
    </div>
    <ul class="swiper-btns">
      <li class="btn" v-for="(item, index) in swiperUrls"></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "SwiperItem",
  props: {
    swiperUrls: {
      type: Array,
    },
  },
  data() {
    return {
      curIndex: 0,
      imgsLength: 0,
      imgs: [],
    };
  },
  mounted() {
    let imgBox = document.getElementsByClassName("image")[0];
    this.imgs = document.getElementsByClassName("img-item");
    this.imgsLength = this.imgs.length;

    if (this.imgsLength > 1) {
      let preNode = this.imgs[this.imgsLength - 1].cloneNode(true);
      imgBox.appendChild(this.imgs[0].cloneNode(true));
      imgBox.insertBefore(preNode, this.imgs[0]);
    }
  },
  methods: {
    goLeft() {
      this.curIndex++;
      for (let i = 0; i < this.imgs.length; i++) {
        this.imgs[i].style.left = -this.curIndex * 1226 + "px";
      }
    },
    goRight() {
      this.curIndex--;
      for (let i = 0; i < this.imgs.length; i++) {
        this.imgs[i].style.left = -this.curIndex * 1226 + "px";
      }
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
  /* overflow: hidden; */
  cursor: pointer;
}

.image {
  display: flex;
  width: 100%;
}
.image img {
  width: 100%;
  position: relative;
  left: -1226px;
  transition: 0.5s;
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
</style>
