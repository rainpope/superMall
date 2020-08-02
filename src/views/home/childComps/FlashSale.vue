<template>
  <div id="home-flashsale">
    <div class="flashsale-hd">
      <h2 class="title">小米闪购</h2>
    </div>

    <div class="flashsale-bd">
      <div class="flashsale-countdown">
        <div class="start-time">10:00 场</div>
        <img :src="falsh" alt="" />
        <div class="flash-text">本场已结束</div>
        <div class="countdown">
          <span>00</span>
          <i>:</i>
          <span>00</span>
          <i>:</i>
          <span>00</span>
        </div>
      </div>

      <div class="flashsale-list">
        <ul class="swiper-wrapper">
          <li class="swiper-slide" v-for="item in commodity" :style="{borderTopColor: item.topStyle}">
            <a href="#">
              <div class="content">
                <div class="thumb">
                  <img :src="item.img" alt="" />
                </div>
                <h3 class="title">{{ item.title }}</h3>
                <p class="desc">{{ item.text }}</p>
                <p class="price">
                  <span>{{ item.price }}元</span>
                  <del>{{ item.rawPrice }}元</del>
                </p>
              </div>
            </a>
          </li>
        </ul>
      </div>
    </div>

    <div class="swiper-list-btn">
      <span>
        &lt;
      </span>
      <span>
        &gt;
      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: "FlashSale",
  data() {
    return {
      falsh: `data:img/jpg;base64,iVBORw0KGgoAAAANSUhEUgAAACIAAAA1CAYAAAAklDnhAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJ
bWFnZVJlYWR5ccllPAAAAyNpVFh0WE1MOmNvbS5hZG9iZS54bXAAAAAAADw/eHBhY2tldCBiZWdp
bj0i77u/IiBpZD0iVzVNME1wQ2VoaUh6cmVTek5UY3prYzlkIj8+IDx4OnhtcG1ldGEgeG1sbnM6
eD0iYWRvYmU6bnM6bWV0YS8iIHg6eG1wdGs9IkFkb2JlIFhNUCBDb3JlIDUuNS1jMDE0IDc5LjE1
MTQ4MSwgMjAxMy8wMy8xMy0xMjowOToxNSAgICAgICAgIj4gPHJkZjpSREYgeG1sbnM6cmRmPSJo
dHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4gPHJkZjpEZXNjcmlw
dGlvbiByZGY6YWJvdXQ9IiIgeG1sbnM6eG1wPSJodHRwOi8vbnMuYWRvYmUuY29tL3hhcC8xLjAv
IiB4bWxuczp4bXBNTT0iaHR0cDovL25zLmFkb2JlLmNvbS94YXAvMS4wL21tLyIgeG1sbnM6c3RS
ZWY9Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC9zVHlwZS9SZXNvdXJjZVJlZiMiIHhtcDpD
cmVhdG9yVG9vbD0iQWRvYmUgUGhvdG9zaG9wIENDIChNYWNpbnRvc2gpIiB4bXBNTTpJbnN0YW5j
ZUlEPSJ4bXAuaWlkOjY4Q0ZFMkY5MTJFNzExRThCMkM4OEM1RTNBNjczQUVBIiB4bXBNTTpEb2N1
bWVudElEPSJ4bXAuZGlkOjY4Q0ZFMkZBMTJFNzExRThCMkM4OEM1RTNBNjczQUVBIj4gPHhtcE1N
OkRlcml2ZWRGcm9tIHN0UmVmOmluc3RhbmNlSUQ9InhtcC5paWQ6NjhDRkUyRjcxMkU3MTFFOEIy
Qzg4QzVFM0E2NzNBRUEiIHN0UmVmOmRvY3VtZW50SUQ9InhtcC5kaWQ6NjhDRkUyRjgxMkU3MTFF
OEIyQzg4QzVFM0E2NzNBRUEiLz4gPC9yZGY6RGVzY3JpcHRpb24+IDwvcmRmOlJERj4gPC94Onht
cG1ldGE+IDw/eHBhY2tldCBlbmQ9InIiPz5oEyacAAACoklEQVR42sSYv0tbURTHX0LqD6T4g4pE
cHDoUOloBxVd/QFFEcQqWtrSKlKFmmAslopohzgIbv4FwUEE0clFujiIi+BSIbRQ0ooKRReRULHf
S48Qgu++c3/FAx+iyU3eJzf3nnPuC/1qavQ04zVY8szjCHRGNN9cBD6DSkOJKzAGzsOaH/AW1FuY
jRg4EH/oiJSCTxYk1sDK7T86Iu9BraHED/Au9wlVkYdg2lAiC/rBhYnIB/DIUOQj2M9/UkWkCsQN
JbbA8l0vqIhMgXIDiZ/gFbgxEakBEwYSf8Eg+OM3gCsyA8oMRETy25UN4IjUgVEDiW2wGDSIIzIL
ijUljsFLv3WhIvKYFphOXNO6OOUMDhKZA7qFcQF85Q6WXeQpeKEpcULlvY8xthp8iwR8I93qLLb7
KnOsSPWNfhd6Bro99yHqTi9IhyWzEXIsIXbSG7Djt1jbQHsBZkMkyZRs13wpgIRoiJKy7dsBWh1L
bN5Vt3JFQrQ2XMYeGKBk5yvSI7aRQ4k0eA4uZZlVPM47lDgTZxd6lKb4AcqkLuKSZiIdVGsiVFNc
xDV9yT1Orekjoe+MDw4pHqwmaJewit66Ql0QaX+DOTaZe4DitAFZxQaaEynKnJ6KCDeaQAtj3A7V
kBtXIpwT3iFV06zqquaKPKEtKIsM6Mo/StoWiQeMvSCJjO4+54hEwTCjuTk0STgckUm6QxTY3LgU
Kc+/jyFrblyKCIkKbnPjSkT8HDGV5saVyBAtVHZz40Ik7HNTRtrcuBARF2tQbW5ciCR0mhvbIs2E
cnNjWySh29zYFGnIK25KzY1Nkdziptzc2BKJUu7Qbm5sicQom2o3NzZEKqiu/DZpbmyIjIAHNBMZ
7x4iTALjhcgVQSIl3v87w5vePcY/AQYAFYR6skFSqBUAAAAASUVORK5CYII=`,
      isshow: false,
      topStyle: ["#ffac13", "#83c44e", "2196f3", "#e53935", "#00c0a5"],
      commodity: [
        {
          img:
            "//cdn.cnbj0.fds.api.mi-img.com/b2c-shopapi-pms/pms_1571379913.70266745.jpg?thumb=1&w=200&h=200",
          title: "米家吸顶灯 卧室吸顶灯350",
          text: "开启全屋智能照明时代",
          price: 229,
          rawPrice: 249,
        },
        {
          img:
            "//cdn.cnbj0.fds.api.mi-img.com/b2c-shopapi-pms/pms_1578383527.34345631.jpg?thumb=1&w=200&h=200",
          title: "米家电动剃须刀S500C 黑色",
          text: "一机三用，面面俱到",
          price: 259,
          rawPrice: 299,
        },
        {
          img:
            "//cdn.cnbj0.fds.api.mi-img.com/b2c-shopapi-pms/pms_1559097300.03074345.jpg?thumb=1&w=200&h=200",
          title: "米家台灯1S 白色",
          text: "A 级光学照度",
          price: 159,
          rawPrice: 179,
        },
        {
          img:
            "//cdn.cnbj0.fds.api.mi-img.com/b2c-mimall-media/e277547c6e3329303dd2c20a327424c4.jpg?thumb=1&w=200&h=200",
          title: "小米AI音箱",
          text: "听音乐、语音遥控家电",
          price: 199,
          rawPrice: 299,
        },
        {
          img:
            "//cdn.cnbj0.fds.api.mi-img.com/b2c-shopapi-pms/pms_1555486031.585971.jpg?thumb=1&w=200&h=200",
          title: "小米净水器600G 白色",
          text: "600加仑通量，流速更快",
          price: 1699,
          rawPrice: 2499,
        },
      ],
    };
  },
  mounted() {
    for (let i = 0, j = 0; i < this.commodity.length; i++, j++) {
      if (j > 4) {
        j = 0;
      }
      this.commodity[i].topStyle = this.topStyle[j]
    }
  },
};
</script>

<style scoped>
#home-flashsale {
  width: 1226px;
  height: 398px;
  margin: auto;
  position: relative;
}
.flashsale-hd {
  width: 100%;
  height: 58px;
}
.flashsale-hd .title {
  font-size: 22px;
  line-height: 58px;
  color: #333;
  font-weight: 200;
}

.flashsale-countdown {
  width: 234px;
  height: 300px;
  padding-top: 39px;
  border-top: 1px solid red;
  background: #f1eded;
  text-align: center;
  box-sizing: content-box;
  float: left;
}

.flashsale-countdown img {
  display: inline-block;
  margin: 25px 0;
}

.flashsale-countdown .start-time {
  height: 24px;
  color: red;
  font-size: 21px;
  padding-top: 15px;
  box-sizing: content-box;
}

.flashsale-countdown .flash-text {
  color: rgba(0, 0, 0, 0.54);
}

.flashsale-countdown .countdown {
  width: 175px;
  margin: 28px 33px 0;
}
.flashsale-countdown .countdown span {
  display: inline-block;
  width: 46px;
  height: 46px;
  background-color: #605751;
  line-height: 46px;
  color: #ffffff;
  font-size: 24px;
  font-weight: 700px;
}
.flashsale-countdown .countdown i {
  font-style: normal;
  font-size: 28px;
  /* font-weight: 500; */
  margin: 0 5px;
}

.flashsale-list {
}

.flashsale-list .swiper-wrapper {
  display: flex;
  overflow: hidden;
}

.flashsale-list .swiper-slide {
  width: 234px;
  height: 339px;
  margin-left: 14px;
  background-color: #ffffff;
  box-sizing: content-box;
  cursor: pointer;
  border-top-width: 1px;
  border-top-style: solid;
}
.swiper-slide a {
  display: block;
  padding-top: 39px;
  /* box-sizing: content-box; */
}
.swiper-slide .thumb {
  margin: 0 37px 22px;
}
.swiper-slide .thumb img {
  width: 160px;
}
.flashsale-list .title {
  display: block;
  width: 194px;
  font-size: 14px;
  font-weight: 400;
  text-overflow: ellipsis;
  text-align: center;
  margin: 0 20px 5px;
  color: #000;
}
.flashsale-list .desc {
  display: block;
  width: 194px;
  text-align: center;
  margin: 0 20px 12px;
  color: rgba(0, 0, 0, 0.4);
  font-size: 11px;
}
.flashsale-list .price {
  display: block;
  text-align: center;
}
.flashsale-list .price span {
  color: #ff6709;
}
.flashsale-list .price del {
  margin-left: 5px;
  color: rgba(0, 0, 0, 0.4);
}

.swiper-list-btn {
  width: 70px;
  height: 25px;
  background-color: #f5f5f5;
  position: absolute;
  right: 0;
  top: 24px;
}
.swiper-list-btn span {
  width: 50%;
  display: inline-block;
  text-align: center;
  font-size: 20px;
  color: #b0b0b0;
  transition: 0.4s;
  border: 1px solid #e0e0e0;
}
.swiper-list-btn span:nth-child(1) {
  border-right: none;
}

.swiper-list-btn span:hover {
  color: #ff6709;
}
</style>
