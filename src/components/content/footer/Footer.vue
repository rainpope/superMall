<template>
  <div class="footer">
    <div class="service">
      <div>
        <p>
          <a href=""
            ><i class="iconfont iconbanshou"></i><span>预约维修服务</span></a
          >
        </p>
      </div>
      <div>
        <p>
          <a href=""
            ><i class="iconfont icon7tiantuihuanhuo"></i
            ><span>7天无理由退货</span></a
          >
        </p>
      </div>
      <div>
        <p>
          <a href=""
            ><i class="iconfont icon15tianwuliyoutuihuo"></i
            ><span>15天免费换货</span></a
          >
        </p>
      </div>
      <div>
        <p>
          <a href=""
            ><i class="iconfont iconliwu"></i><span>满99元包邮</span></a
          >
        </p>
      </div>
      <div>
        <p>
          <a href=""
            ><i class="iconfont icondingwei"></i><span>520余家售后网点</span></a
          >
        </p>
      </div>
    </div>

    <div class="links">
      <dl>
        <dt>帮助中心</dt>
        <dd><a href="">账号管理</a></dd>
        <dd><a href="">购物指南</a></dd>
        <dd><a href="">订单操作</a></dd>
      </dl>
      <dl>
        <dt>服务支撑</dt>
        <dd><a href="">售后政策</a></dd>
        <dd><a href="">自助服务</a></dd>
        <dd><a href="">相关下载</a></dd>
      </dl>
      <dl>
        <dt>线下门店</dt>
        <dd><a href="">小米之家</a></dd>
        <dd><a href="">服务网点</a></dd>
        <dd><a href="">授权体验店</a></dd>
      </dl>
      <dl>
        <dt>关于小米</dt>
        <dd><a href="">了解小米</a></dd>
        <dd><a href="">加入小米</a></dd>
        <dd><a href="">投资者关系</a></dd>
        <dd><a href="">企业社会责任</a></dd>
        <dd><a href="">廉洁举报</a></dd>
      </dl>
      <dl>
        <dt>关注我们</dt>
        <dd><a href="">新浪微博</a></dd>
        <dd><a href="">官方微信</a></dd>
        <dd><a href="">联系我们</a></dd>
        <dd><a href="">公益基金会</a></dd>
      </dl>
      <dl>
        <dt>特色服务</dt>
        <dd><a href="">F 码通道</a></dd>
        <dd><a href="">礼物码</a></dd>
        <dd><a href="">防伪查询</a></dd>
      </dl>
      <dl class="end">
        <dt>400-100-5678</dt>
        <dd class="dh">8:00-18:00 (仅收市话费)</dd>
        <dd class="rg">
          <i class="iconfont iconxiaoxi"></i>
          人工客服
        </dd>
        <dd class="gz">
          关注小米:
          <a href=""><i class="iconfont iconweibo"></i></a>
          <a href=""><i class="iconfont icongongzhonghao"></i></a>
        </dd>
      </dl>
    </div>

    <div class="info-text">
      <p class="sites">
        <span v-for="(item, index) in infoText">
          <a :href="item.url">{{ item.title }}</a>
          <span v-if="index != infoText.length - 1">丨</span>
        </span>
      </p>
      <p>
        ©<a href="">mi.com</a>
        <span>京ICP证110507号</span>
        <a href="">京ICP备10046444号</a>
        <a href="">京公网安备11010802020134号</a>
        <a href="">京网文[2020]0276-042号</a>
        <br />
        <a href="">（京）网械平台备字（2018）第00005号</a>
        <a href="">互联网药品信息服务资格证 (京)-非经营性-2014-0090</a>
        <a href="">营业执照</a>
        <a href="">医疗器械质量公告</a>
        <br />
        <a href="">增值电信业务许可证</a>
        <span> 网络食品经营备案 京食药网食备201810017</span>
        <a href="">食品经营许可证</a>
        <br />
        <span>违法和不良信息举报电话：171-5104-4404</span>
        <a href="">知识产权侵权投诉</a>
        <span>本网站所列数据，除特殊说明，所有数据均出自我司实验室测试</span>
      </p>
    </div>

    <div class="footer-end-img">
      <img src="//i1.mifile.cn/f/i/17/site/truste.png" alt="" />
      <img src="//s01.mifile.cn/i/v-logo-2.png" alt="" />
      <img src="//s01.mifile.cn/i/v-logo-1.png" alt="" />
      <img
        src="//i8.mifile.cn/b2c-mimall-media/ba10428a4f9495ac310fd0b5e0cf8370.png"
        alt=""
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "Footer",
  data() {
    return {
      infoText: [
        { title: "小米商城", url: "/" },
        { title: "MIUI", url: "#" },
        { title: "米家", url: "#" },
        { title: "米聊", url: "#" },
        { title: "多看", url: "#" },
        { title: "游戏", url: "#" },
        { title: "政企服务", url: "#" },
        { title: "小米天猫店", url: "#" },
        { title: "小米集团隐私政策", url: "#" },
        { title: "小米公司儿童信息保护规则", url: "#" },
        { title: "小米商城隐私政策", url: "#" },
        { title: "小米商城用户协议", url: "#" },
        { title: "问题反馈", url: "#" },
        { title: "Select Location", url: "#" },
      ],
    };
  },
};
</script>

<style scoped>
.footer {
  width: 1226px;
  margin: auto;
}
/* 服务的样式 */
.service {
  display: flex;
  height: 79px;
  border-bottom: 1px solid #e0e0e0;
}
.service div {
  flex: 1;
  text-align: center;
  font-size: 18px;
  padding: 27px 0;
}
.service div p {
  border-right: 1px solid #e0e0e0;
}
.service div:last-child p {
  border-right: none;
}
.service div i {
  position: relative;
  margin-right: 5px;
  font-size: 25px;
  top: 3px;
}
.service div a {
  color: #333;
  transition: 0.3s;
}
.service div a:hover {
  color: #ff6700;
}

/* 页脚连接的样式 */
.links {
  display: flex;
  padding: 40px 0;
}
.links dl {
  height: 112px;
  flex: 1;
}
.links .end {
  width: 245px;
  border-left: 1px solid #eeeeee;
  flex: none;
}
.links dt {
  font-size: 14px;
  margin-bottom: 26px;
  color: #454545;
}
.links dd {
  margin-top: 10px;
}
.links a {
  color: #757575;
  font-size: 12px;
}
.links a:hover {
  color: #ff6700;
}
/* 页脚连接最后一个的控制 */
.links .end {
  text-align: center;
}
.links .end dt {
  color: #ff6700;
  font-size: 22px;
  margin-bottom: 5px;
}
.links .end .dh {
  margin-top: 0;
  font-size: 12px;
  color: #757575;
  margin-bottom: 5px;
}
.links .end .rg {
  width: 120px;
  height: 30px;
  border: 1px solid #ff6700;
  color: #ff6700;
  font-size: 12px;
  line-height: 28px;
  margin: auto;
  cursor: pointer;
  transition: 0.3s;
}
.links .end .rg:hover {
  background-color: #ff6700;
  color: #fff;
}
.links .rg i {
  font-size: 10px;
}
.links .end .gz {
  font-size: 12px;
  color: #757575;
  line-height: 12px;
}
.links .gz i {
  position: relative;
  top: 4px;
  margin-left: 5px;
  font-size: 25px;
  color: #333;
}
.links .gz i:hover {
  color: #ff6700;
}

/* info text */
.sites {
  font-size: 14px;
  color: #757575;
  margin-top: 35px;
  margin-bottom: 15px;
}
.sites span span {
  margin: 0 2px;
}

.info-text p:last-child a {
  margin: 0 5px;
}
.info-text a:hover {
  color: #ff6700;
}

/* 底部图片 */
.footer-end-img {
  margin-top: 20px;
}
.footer-end-img img{
 display: inline-block;
 margin-right: 5px;
}
</style>
