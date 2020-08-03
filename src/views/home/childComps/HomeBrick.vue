<template>
  <div class="home-brick">
    <div class="brick-hd">
      <div class="titile">
        <h2></h2><slot name='brick-hd-title'></slot></h2>
      </div>
    </div>

    <div class="brick-bd">
      <div class="brick-img">
        <ul>
          <li v-for="item in brickImg">
            <a :href="item.url">
              <img :src="item.img" alt="" />
            </a>
          </li>
        </ul>
      </div>

      <div class="brick-list">
        <div class="brick-item">
          <ul>
            <li v-for="(item,index) in itemShow" :class="{endLi: index == itemShow.length-1 && !isone}">
                <div class="end-s">
                  <img :src="item.img" alt="" />
                  <!-- <h3 class="title">{{item.title}}</h3> -->
                  
                  <div v-if="isone || (index != itemShow.length-1)">
                    <h3 class="title">{{item.title}}</h3>
                    <p class="text">{{item.text}}</p>
                    <p class="price">
                    <span v-if="item.minprice == null" >{{item.newprice}}元</span>
                    <span v-else >{{item.minprice}}元起</span>
                    <del v-if="item.oldprice != null">{{item.oldprice}}元</del>
                    </p>
                  </div>
                  <div v-if="index == itemShow.length-1 && !isone " class="end-price">
                    <h3 class="title">{{item.title}}</h3>
                    <span v-if="item.minprice == null" >{{item.newprice}}元</span>
                    <span v-else >{{item.minprice}}元起</span>
                  </div>
              </div>

                <div v-if="index == itemShow.length-1 && !isone ">
                      <div class="more" >
                        <div class="more-text">
                          <span>浏览更多</span>
                          <span>{{itemtitle}}</span>
                        </div>
                        <div class="right iconfont iconright">
                        </div>
                    </div>
                </div>
            </li>
          </ul>
        </div>
      </div>
    </div>

    <div class="brick-list-btns">
      <ul>
        <li 
        v-for="(item, index) in brickItem" 
        @mouseenter="tabList(index,item.title)"
        :class="{btnActive:index == itemIndex && brickItem.length > 1}"
        >
          {{item.title}}
        <span v-if="brickItem.length <= 1">&gt;</span>          
        </li>
      </ul>
    </div>

  </div>
</template>

<script>
export default {
  name: "HomeBrick",
  props: {
    brickImg: {
      type: Array,
        default() {
          return []
        }
      },
    brickItem: {
      type: Array,
        default() { 
          return []
        }
      }
  },
  data() {
    return {
      itemIndex: 0,
      itemtitle: "热门",
      isone: null,
    };
  }, 
  mounted() {
    // 判断是不是只有一个选项，如果是那么最后一个会不一样显示
    if(this.brickItem.length > 1){
      this.isone = false;
    }else{
      this.isone = true;
    }
    this.itemIndex = this.brickItem.length -1
  },
  computed: {
    itemShow() {
      return this.brickItem[this.itemIndex].item
    },
  }, 
  methods: {
    tabList(index, title) {
      this.itemIndex = index;
      this.itemtitle = title;
    }
  },
  
};
</script>

<style scoped>
  .home-brick {
    width: 1226px;
    height: 672px;
    margin: auto;
    position: relative;
  }
  .brick-hd {
    width: 1226px;
    height: 58px;
    font-size: 22px;
    font-weight: 200;
    line-height: 58px;
    color: #333;
  }

  .brick-bd{
    width: 100%;
    display: flex;
  }
  .brick-img{
    width: 234px;
  }
  .brick-img img{
    position: relative;
    transition: 0.3s;
    top: 0;
  }
  .brick-img li:nth-child(2) {
    margin-top: 14px;
  }

  .brick-img img:hover{
    top: -5px;
    box-shadow: 1px 1px 15px #c0c0c0;
  }
  .brick-list {
    flex: 1 ;
  }
  .brick-item ul {
    display: flex;
    flex-wrap: wrap;
  }
  .brick-item li {
    position: relative;
    width: 234px;
    height: 300px;
    margin-left: 14px;
    margin-bottom: 14px;
    background-color: #fff; 
    transition: 0.3s;
    top:0;
    cursor: pointer;
  }
  .brick-item li:hover {
    top: -5px;
    box-shadow: 1px 1px 15px #c0c0c0;
  }
  .brick-item li {
    text-align: center;
    white-space: nowrap;
    font-size: 14px;
    padding: 20px 0;
  }
  .brick-item li img{
    width: 160px;
    height: 160px;
    margin: auto;
    margin-bottom: 20px;
  }
  .brick-item .title {
    width: 214px;
    font-weight: 400;
    color: #333;
    display: block;
    margin: 0 10px 7px 10px;
    text-overflow: ellipsis;
  }
  .brick-item .text {
    width: 214px;
    font-size: 12px;
    color: rgba(0, 0, 0, 0.4);
    display: block;
    margin: 0 10px 20px 10px;
    overflow: hidden;
    text-overflow: ellipsis;
  }
  .brick-item .price {
    width: 214px;
    color: #ff6700;
    display: block;
    margin: 0 10px 10px 10px;
    text-overflow: ellipsis;
  }
  .brick-item .price del {
    color: rgba(0, 0, 0, 0.4);
    margin-left: 5px;
  }
  /* 如何是两个广告图控制最后一个的样式 */
  .brick-item .endLi {
    background-color: #F5F5F5;
    color: #ff6700;
    padding: 0;
    cursor: auto;
  }
  .brick-item .endLi:hover{
    top: 0;
    box-shadow: none;
  }
  .brick-item .endLi img {
    width: 80px;
    height: 80px;
  }
  .endLi .end-s {
    height: 143px;
    position: relative;
    background-color: #fff;
    top: 0;
    transition: 0.5s;
    cursor: pointer;
  }
  .endLi .end-s:hover {
    top: -5px;
    box-shadow: 1px 1px 20px #c0c0c0;
  }
  .endLi .end-s img {
    position: absolute;
    top: 30px;
    right: 20px;
  }
  .endLi .end-s .end-price {
    position: absolute;
    text-align: left;
    white-space: pre-wrap;
    top: 40px;
    left: 25px;
  }
  .endLi .end-price .title {
    width: 94px;
    margin: 0;
    font-size: 14px;
    margin-bottom: 10px;
  }
  /* 列表最后一个元素的更多选项 */
  .brick-item .endLi .more {
    margin-top: 14px;
    height: 143px;
    background-color: #fff;
    color: #000;
    position: relative;
    top: 0;
    transition: 0.5s;
    cursor: pointer;
  }
  .brick-item .endLi .more:hover {
    top: -5px;
    box-shadow: 1px 1px 20px #c0c0c0;
  }
  .brick-item .more .more-text {
    width: 45px;
    position: absolute;
    left: 30px;
    top: 50px;
  }
  .more .more-text span{
    display: block;
    text-align: left;
  }
  .more .more-text span:nth-child(1) {
    font-size: 20px;
    color: #333;
  }
  .more .more-text span:nth-child(2) {
    margin-top: 5px;
    color: rgba(0, 0, 0, 0.5);
  }
  .more .right {
    position: absolute;
    width: 50px;
    height: 50px;
    border: 3px solid #ff6700;
    border-radius: 50%;
    color: #ff6700;
    line-height: 45px;
    text-align: center;
    font-size: 25px;
    font-weight: 1000;
    right: 40px;
    top: 45px;
  }


  /* 列表控制按钮 */
  .brick-list-btns {
    position: absolute;
    right: 0;
    top: 24px;
    color: #333;
    transition: 0.5s;
  }
  .brick-list-btns li {
    float: right;
    margin-left: 30px;
    transition: 0.2s;
    padding-bottom: 3px;
    border-bottom: 2px;
  }

  .brick-list-btns li:hover {
    color: #ff6700;
  }
  .brick-list-btns li:hover span {
    background-color: #ff6700;
  }

  .brick-list-btns span {
    display: inline-block;
    width: 20px;
    height: 20px;
    background-color: #B0B0B0;
    color: #fff;
    margin-left: 5px;
    border-radius: 50%;
    text-align: center;
    font-weight: 700;
    transition: 0.5s;
  }

  .brick-list-btns .btnActive {
    color: #ff6700;
    border-bottom: 3px solid #ff6700;
  }
</style>
