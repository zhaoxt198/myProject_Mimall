<template>
  <div class="footer">
    <div class="site-footer">
      <div class="container">
        <div class="footer-service">
            <service-bar></service-bar>
          <!-- <ul class="list-service">
            <li><a href=""><span class="icon-setting"></span>预约维修服务</a></li>
            <li><a href=""><span class="icon-7day"></span>7天无理由退货</a></li>
            <li><a href=""><span class="icon-15day"></span>15天免费换货</a></li>
            <li><a href=""><span class="icon-post"></span>满69元包邮</a></li>
            <li><a href=""><span class="icon-service"></span>1100余家售后网点</a></li>
          </ul> -->
        </div>
        <div class="footer-links">
          <dl class="col-links col-links-first"><dt></dt></dl>
          <dl class="col-links">
            <dt>选购指南</dt>
            <dd><a href="">手机</a></dd>
            <dd><a href="">电视</a></dd>
            <dd><a href="">笔记本</a></dd>
            <dd><a href="">平板</a></dd>
            <dd><a href="">穿戴</a></dd>
            <dd><a href="">耳机</a></dd>
            <dd><a href="">家电</a></dd>
            <dd><a href="">路由器</a></dd>
            <dd><a href="">音箱</a></dd>
            <dd><a href="">配件</a></dd>
          </dl>
          <dl class="col-links">
            <dt>服务中心</dt>
            <dd><a href="">申请售后</a></dd>
            <dd><a href="">售后政策</a></dd>
            <dd><a href="">维修服务价格</a></dd>
            <dd><a href="">订单查询</a></dd>
            <dd><a href="">以旧换新</a></dd>
            <dd><a href="">保障服务</a></dd>
            <dd><a href="">防伪查询</a></dd>
            <dd><a href="">F码通道</a></dd>
          </dl>
          <dl class="col-links">
            <dt>线下门店</dt>
            <dd><a href="">小米之家</a></dd>
            <dd><a href="">服务网点</a></dd>
            <dd><a href="">授权体验店/专区</a></dd>
          </dl>
          <dl class="col-links">
            <dt>关于小米</dt>
            <dd><a href="">了解小米</a></dd>
            <dd><a href="">加入小米</a></dd>
            <dd><a href="">投资者关系</a></dd>
            <dd><a href="">环境，社会及管制</a></dd>
            <dd><a href="">廉洁举报</a></dd>
          </dl>
          <dl class="col-links">
            <dt>关注我们</dt>
            <dd><a href="">新浪微博</a></dd>
            <dd><a href="">官方微信</a></dd>
            <dd><a href="">联系我们</a></dd>
            <dd><a href="">公益基金会</a></dd>
          </dl>
          <dl class="col-contact">
            <p class="phone">400-100-5678</p>
            <p class="tip">8:00-18:00（仅收市话费）</p>
            <a href="" class="btn-line-primary">人工客服</a>
          </dl>
        </div>
      </div>
    </div>
    <div class="site-info">
      <div class="container">
        <div class="logo"><img src="/imgs/logo-mi.png" /></div>
        <div class="info-text">
          <p class="sites1">
            <a href="">小米商城</a><span>|</span> 
            <a href="">MIUI</a><span>|</span> 
            <a href="">米家</a><span>|</span> 
            <a href="">米聊</a><span>|</span>
            <a href="">多看</a><span>|</span> 
            <a href="">游戏</a><span>|</span> 
            <a href="">政企服务</a><span>|</span>
            <a href="">小米天猫店</a><span>|</span>
            <a href="">小米集团隐私政策</a><span>|</span>
            <a href="">小米公司儿童信息保护规则</a><span>|</span>
            <a href="">小米商城隐私政策</a><span>|</span>
            <a href="">小米商城用户协议</a><span>|</span> 
            <a href="">问题反馈</a><span>|</span>
            <a href="">Select Location</a>
          </p>
          <p class="sites2">
            <a href="">北京互联网法院法律服务工作站</a><span>|</span>
            <a href="">中国消费者协会</a><span>|</span>
            <a href="">北京市消费者协会</a>
          </p>
          <p class="sites3">
            ©
            <a href="" target="_blank">mi.com</a>
            <a href="">京ICP证110507号</a><a href="">京ICP备10046444号</a><a href="">京公网安备11010802020134号</a><a href="">京网文[2020]0276-042号</a><br />
            <a href="">（京）网械平台备字（2018）第00005号</a><a href="">互联网药品信息服务资格证</a><a href="">(京)-非经营性-2014-0090</a><a href="">营业执照</a><a href="">医疗器械质量公告</a><br />
            <a href="">增值电信业务许可证</a>网络食品经营备案&nbsp;京食药网食备202010048&nbsp;<a href="">食品经营许可证</a><br />
            违法和不良信息举报电话：171-5104-4404<a href="">知识产权侵权投诉</a>本网站所列数据，除特殊说明，所有数据均出自我司实验室测试
          </p>
        </div>
        <div class="info-links">
          <a href=""><img src="/imgs/footer/info-links1.jpg" /></a>
          <a href=""><img src="/imgs/footer/info-links2.jpg" /></a>
          <a href=""><img src="/imgs/footer/info-links3.jpg" /></a>
          <a href=""><img src="/imgs/footer/info-links4.jpg" /></a>
          <a href=""><img src="/imgs/footer/info-links5.jpg" /></a>
        </div>
      </div>
      <div class="slogan"><img src="/imgs/footer/slogan2020.jpg" /></div>
    </div>
  </div>
</template>
<script>
import ServiceBar from "../components/ServiceBar";
export default {
  name: "nav-footer",
  components: {ServiceBar}
};
</script>

<style lang="scss" scoped>
@import "./../assets/scss/mixin.scss";
.footer {
  display: block;
  -webkit-text-size-adjust: 100%;
  a {
    color: #757575;
    text-decoration: none;
    margin-right: 5px;
    margin-left: 5px;
  }
  a:hover {
    color: #ff6700;
  }
  .site-footer {
    display: block;
    .container {
      width: 1226px;
      margin-right: auto;
      margin-left: auto;
      display: block;
      .footer-links {
        display: block;
        padding: 40px 0;
        height: 310px;
        .col-links {
          float: left;
          width: 160px;
          margin: 0;
        }
        dl {
          display: block;
          dt {
            display: block;
            margin: -1px 0 26px;
            line-height: 1.25;
            font-size: 14px;
            color: #424242;
          }
          dd {
            margin: 10px 0 0;
            font-size: 12px;
            display: block;
            a {
              color: #757575;
              cursor: pointer;
            }
            a:hover {
              color: #ff6700;
              text-decoration: none;
            }
          }
        }
        .col-contact {
          float: right;
          display: block;
          width: 251px;
          border-left: 1px solid #e0e0e0;
          text-align: center;
          color: #616161;
          .phone {
            font-size: 22px;
            line-height: 1;
            color: #ff6700;
          }
          .tip {
            margin: 0 0 5px 0;
            display: block;
          }
          .btn-line-primary {
            display: inline-block;
            border: 1px solid #b0b0b0;
            text-align: center;
            cursor: pointer;
            border-color: #ff6700;
            color: #ff6700;
            background-color: #fff;
            width: 118px;
            height: 28px;
            font-size: 12px;
            line-height: 28px;
            &:before{
              @include bgImg(17px,17px,'/imgs/contact.svg');
              content: "";
              color: #ff6700;
              border-color: #ff6700;
              margin-right: 5px;
              vertical-align: middle;
            }
          }
          a:hover {
            color: #fff;
            background-color: #ff6700;
            text-decoration: none;
            &:before{
              @include bgImg(17px,17px,'/imgs/contact1.svg');
            }
          }
        }
      }
    }
  }
  .site-info {
    display: block;
    padding: 30px 0;
    font-size: 12px;
    background-color: #fafafa;
    .container {
      position: relative;
      display: block;
      width: 1226px;
      margin-right: auto;
      margin-left: auto;
      .logo {
        position: absolute;
        display: block;
        width: 56px;
        height: 56px;
        margin-right: 20px;
        background-size: 56px;
        img {
          display: block;
          width: 56px;
          height: 56px;
          text-align: left;
          overflow: hidden;
        }
      }
      .info-text {
        color: #b0b0b0;
        padding-left: 77px;
        display: block;
        font-size: 12px;
        .sites1 .sites2 .sites3 {
          margin: 0;
          line-height: 18px;
          display: block;
          margin-bottom: 5px;
        }
        .sites3 > a {
          color: #b0b0b0;
        }
        a:hover{
          color: #ff6700;
        }
      }
      .info-links {
        display: block;
        height: 28px;
        margin: 4px 0 15px;
        padding-left: 77px;
        a {
          display: inline-block;
          img {
            border: 0;
            width: auto;
            height: 28px;
            margin-left: 0;
            cursor: pointer;
          }
        }
      }
    }
    .slogan {
      display: block;
      position: absolute;
      width: 100%;
      height: 50px;
      margin-top: 20px;
      img {
        display: block;
        overflow: hidden;
        margin: 0 auto;
        width: auto;
        height: 22px;
      }
    }
  }
}
</style>
