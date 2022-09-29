<template>
  <div class="header">
    <div class="nav-topbar">
      <div class="container">
        <div class="topbar-menu">
          <a href="javascript:;">小米官网</a>
          <a href="javascript:;">小米商场</a>
          <a href="javascript:;">MIUI</a>
          <a href="javascript:;">IoT</a>
          <a href="javascript:;">云服务</a>
          <a href="javascript:;">天星科技</a>
          <a href="javascript:;">有品</a>
          <a href="javascript:;">小爱开放平台</a>
          <a href="javascript:;">企业团购</a>
          <a href="javascript:;">资质证照</a>
          <a href="javascript:;">协议规则</a>
          <a href="javascript:;" class="download">下载APP
            <div class="down-box">
              <b></b><img src="imgs/download.jpg" alt="" /><i>小米商城APP</i>
            </div>
          </a>
          <a href="javascript:;">Select Location</a>
        </div>
        <div class="topbar-user">
          <div class="user">
            <a href="javascript:;" class="user-tit" v-if="username">{{username}}</a>
            <!-- 若未登录，则不显示以下内容 -->
            <div class="user-info" v-if="username">
              <ul>
                <li><a href="">个人中心</a></li>
                <li><a href="">评价晒单</a></li>
                <li><a href="">我的喜欢</a></li>
                <li><a href="">小米账户</a></li>
                <li><a href="javascript:;" v-if="username" @click="loginOut()">退出登录</a></li>
              </ul>
            </div>
          </div>
          <div class="log">
            <a href="javascript:;" v-if="!username" @click="login()">登录</a>
            <a href="javascript:;" v-if="!username" @click="register">注册</a>
            <a href="javascript:;">消息通知</a>
            <a href="/#/order/list" v-if="username">我的订单</a>
            <div class="cart">
              <a href="/#/cart" class="my-cart" @click="goToCart()"><span class="icon-cart"></span>购物车({{ cartCount }})</a>
              <!-- 若商品数量为0，则显示下面内容 -->
              <div class="children" v-if="!cartCount">购物车中还没有商品，赶紧选购吧！</div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="nav-header">
      <div class="container">
        <div class="header-logo"><a href="/#/index"></a></div>

        <div class="header-menu">
          <div class="item-menu">
            <span>Xiaomi手机</span>
            <div class="children">
              <ul>
                <li class="product" v-for="(item, index) in phoneList" :key="index">
                  <a :href="'/#/product/' + item.id" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="item.mainImage" :alt="item.subtitle" />
                    </div>
                    <div class="pro-name">{{ item.name }}</div>
                    <div class="pro-price">{{ item.price | currency }}</div>
                  </a>
                </li>
              </ul>
            </div>
          </div>

          <div class="item-menu">
            <span>Redmi手机</span>
            <div class="children">
              <ul>
                <li class="product">
                  <a href="/#/product/31" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-3-1.jpg'" alt="" />
                    </div>
                    <div class="pro-name">Redmi k50至尊版</div>
                    <div class="pro-price">2999元起</div>
                  </a>
                </li>
                <li class="product">
                  <a href="/#/product/31" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-3-2.jpg'" alt="" />
                    </div>
                    <div class="pro-name">Redmi Note 11T Pro+</div>
                    <div class="pro-price">1999元起</div>
                  </a>
                </li>
                <li class="product">
                  <a href="/#/product/31" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-3-3.jpg'" alt="" />
                    </div>
                    <div class="pro-name">Redmi Note 11T Pro</div>
                    <div class="pro-price">1599元起</div>
                  </a>
                </li>
                <li class="product">
                  <a href="/#/product/31" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-3-4.jpg'" alt="" />
                    </div>
                    <div class="pro-name">Redmi Note 11SE</div>
                    <div class="pro-price">999元起</div>
                  </a>
                </li>
                <li class="product">
                  <a href="/#/product/31" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-3-5.jpg'" alt="" />
                    </div>
                    <div class="pro-name">Redmi 10A</div>
                    <div class="pro-price">699元起</div>
                  </a>
                </li>
                <li class="product">
                  <a href="/#/product/31" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-3-6.jpg'" alt="" />
                    </div>
                    <div class="pro-name">Redmi K50 Pro</div>
                    <div class="pro-price">2999元起</div>
                  </a>
                </li>
              </ul>
            </div>
          </div>

          <div class="item-menu">
            <span>电视</span>
            <div class="children">
              <ul>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-4-1.jpg'" alt="" />
                    </div>
                    <div class="pro-name">Redmi智能电视 X55 2022</div>
                    <div class="pro-price">2199元</div>
                  </a>
                </li>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-4-2.jpg'" alt="" />
                    </div>
                    <div class="pro-name">Redmi智能电视 X65 2022</div>
                    <div class="pro-price">2999元</div>
                  </a>
                </li>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-4-3.jpg'" alt="" />
                    </div>
                    <div class="pro-name">小米电视6 65 OLED</div>
                    <div class="pro-price">6699元</div>
                  </a>
                </li>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-4-4.jpg'" alt="" />
                    </div>
                    <div class="pro-name">小米电视 大师 77 OLED</div>
                    <div class="pro-price">17999元</div>
                  </a>
                </li>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-4-5.jpg'" alt="" />
                    </div>
                    <div class="pro-name">小米透明电视</div>
                    <div class="pro-price">49999元</div>
                  </a>
                </li>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-4-6.jpg'" alt="" />
                    </div>
                    <div class="pro-name">小米电视 大师 65英寸OLED</div>
                    <div class="pro-price">8999元</div>
                  </a>
                </li>
              </ul>
            </div>
          </div>

          <div class="item-menu">
            <span>笔记本</span>
            <div class="children">
              <ul>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-5-1.jpg'" alt="" />
                    </div>
                    <div class="pro-name">Redmi G 游戏本 锐龙版 R5</div>
                    <div class="pro-price">6299元</div>
                  </a>
                </li>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-5-1.jpg'" alt="" />
                    </div>
                    <div class="pro-name">Redmi G Pro 游戏本 2022</div>
                    <div class="pro-price">8999元起</div>
                  </a>
                </li>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-5-1.jpg'" alt="" />
                    </div>
                    <div class="pro-name">Redmi G Pro 游戏本 锐龙版 R7</div>
                    <div class="pro-price">8799元</div>
                  </a>
                </li>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img src="/imgs/nav-img/nav-5-4.jpg" alt="" />
                    </div>
                    <div class="pro-name">Xiaomi Book Pro 14 锐龙版</div>
                    <div class="pro-price">6399元起</div>
                  </a>
                </li>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-5-1.jpg'" alt="" />
                    </div>
                    <div class="pro-name">Redmi G 游戏本 2022</div>
                    <div class="pro-price">7499元起</div>
                  </a>
                </li>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-5-6.jpg'" alt="" />
                    </div>
                    <div class="pro-name">Xiaomi Book Pro 14 2022</div>
                    <div class="pro-price">6799元起</div>
                  </a>
                </li>
              </ul>
            </div>
          </div>

          <div class="item-menu">
            <span>平板</span>
            <div class="children">
              <ul>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-6-1.jpg'" alt="" />
                    </div>
                    <div class="pro-name">小米平板5 Pro 12.4</div>
                    <div class="pro-price">2999元起</div>
                  </a>
                </li>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-6-2.jpg'" alt="" />
                    </div>
                    <div class="pro-name">小米平板5</div>
                    <div class="pro-price">1999元起</div>
                  </a>
                </li>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-6-3.jpg'" alt="" />
                    </div>
                    <div class="pro-name">小米平板5 Pro 5G</div>
                    <div class="pro-price">3349元</div>
                  </a>
                </li>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img src="/imgs/nav-img/nav-6-4.jpg" alt="" />
                    </div>
                    <div class="pro-name">小米平板5 Pro</div>
                    <div class="pro-price">2499元起</div>
                  </a>
                </li>
              </ul>
            </div>
          </div>

          <div class="item-menu">
            <span>家电</span>
            <div class="children">
              <ul>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-7-1.jpg'" alt="" />
                    </div>
                    <div class="pro-name">巨省电|米家空调 新一级1.5匹</div>
                    <div class="pro-price">2299元</div>
                  </a>
                </li>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-7-2.jpg'" alt="" />
                    </div>
                    <div class="pro-name">巨省电 3匹|变频|新一级能效</div>
                    <div class="pro-price">5099元</div>
                  </a>
                </li>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-7-3.jpg'" alt="" />
                    </div>
                    <div class="pro-name">米家扫托机器人1T</div>
                    <div class="pro-price">999元</div>
                  </a>
                </li>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img src="/imgs/nav-img/nav-7-4.jpg" alt="" />
                    </div>
                    <div class="pro-name">米家互联网洗烘一体机10kg</div>
                    <div class="pro-price">1499元</div>
                  </a>
                </li>
              </ul>
            </div>
          </div>

          <div class="item-menu">
            <span>路由器</span>
            <div class="children">
              <ul>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-8-1.jpg'" alt="" />
                    </div>
                    <div class="pro-name">Redmi电竞路由器 AX5400</div>
                    <div class="pro-price">599元</div>
                  </a>
                </li>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-8-2.jpg'" alt="" />
                    </div>
                    <div class="pro-name">小米路由器 AX5400</div>
                    <div class="pro-price">549元</div>
                  </a>
                </li>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-8-3.jpg'" alt="" />
                    </div>
                    <div class="pro-name">小米路由器 AX9000</div>
                    <div class="pro-price">1299元</div>
                  </a>
                </li>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img src="/imgs/nav-img/nav-8-4.jpg" alt="" />
                    </div>
                    <div class="pro-name">Xiaomi HomeWIFI 三频 Mesh路由器</div>
                    <div class="pro-price">17999元</div>
                  </a>
                </li>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-8-5.jpg'" alt="" />
                    </div>
                    <div class="pro-name">小米路由器4A 千兆版</div>
                    <div class="pro-price">129元</div>
                  </a>
                </li>
                <li class="product">
                  <a href="" target="_blank">
                    <div class="pro-img">
                      <img v-lazy="'/imgs/nav-img/nav-8-6.jpg'" alt="" />
                    </div>
                    <div class="pro-name">查看全部<br />小米路由器</div>
                  </a>
                </li>
              </ul>
            </div>
          </div>

          <div class="item-menu"><span>服务中心</span></div>
          <div class="item-menu"><span>社区</span></div>
        </div>

        <div class="header-search">
          <form id="searchForm" action="//search.mi.com/search" method="get" class="search-form">
            <label for="search" class="hide">站内搜索</label>
            <a href="javascript:;" class="msq">
              <input type="text" name="keyword" autocomplete="off" class="search-text">
            </a>
            <div class="search-btn" data-settrack="true">
              <a href="" class=""></a>
            </div>
            <div class="hotwords"></div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template> 

<script>
import { mapState } from "vuex";
import { Message } from 'element-ui';
import "element-ui/lib/theme-chalk/index.css";

export default {
  name: "nav-header",
  data() {
    return {
      phoneList: [],
    };
  },

  computed: {
    //使用计算属性，目的在于之后username发生变化时，前端的页面能够及时更新
    // username(){
    //   return this.$store.state.username;
    // },
    // cartCount(){
    //   return this.$store.state.cartCount;
    // }
    ...mapState(["username", "cartCount"]),
  },

  filters: {
    currency(val) {
      if (!val) return "0.00";
      return "￥" + val.toFixed(2) + "元";
    },
  },

  methods: {
    login() {
      this.$router.push("/login");
    },
    loginOut() {
      this.axios.post("/user/logout").then(() => {
        this.$message.success("退出成功");
        this.$cookie.set("userId", "", { expires: "-1" });
        this.$store.dispatch("saveUserName", "");
        this.$store.dispatch("saveCartCount", "0");
      });
    },
    getProductList() {
      this.axios.get("/products", {
          params: {
            categoryId: "100012",
            //pageSize:6
          },
        })
        .then((res) => {
          if (res.list.length > 6) {
            this.phoneList = res.list.slice(0, 6);
          }
        });
    },
    goToCart() { // 路由跳转
      this.$router.push("/cart");
    },
    getCartCount() {
      this.axios.get("/carts/products/sum").then((res = 0) => {
        //设置res默认值为0，及时res没有获取到参数，也不会报错
        this.$store.dispatch("saveCartCount", res);
      });
    },
    register() {  //注册
      this.axios.post("/user/register", {
          username: "admin1",
          password: "admin1",
          email: "admin1@163.com",
        })
        .then(() => {
          // this.$message.success('注册成功');
          Message.success("注册成功");
        });
    }
  },

  mounted() {
    this.getProductList();
    //$route 获取参数
    //$router 路由跳转
    //获取参数，判断是否是从登录页面跳转过来的
    let params = this.$route.params;
    if (params && params.from == "login") {
      this.getCartCount();
    }
  },
};
</script>

<style lang='scss' scoped>
@import "./../assets/scss/base.scss";
@import "./../assets/scss/config.scss";
@import "./../assets/scss/mixin.scss";
.header {
  .nav-topbar {
    height: 40px;
    line-height: 40px;
    background-color: #333333;
    color: #b0b0b0;
    .container {
      @include flex();
      height: 40px;
      .topbar-menu {
        a { // 设置a为内联块状元素
          display: inline-block;
          color: #b0b0b0;
          margin-right: 17px;
        }
        a:hover {
          color: #fff;
        }
        .download {
          position: relative;
          .down-box {
            /* 设置相对于父元素居中 */
            width: 130px;
            position: absolute;
            background-color: #fff;
            left: 50%;
            margin-left: -65px;
            top: 40px;
            padding-top: 20px;
            box-shadow: 0 1px 5px #aaa;//图片阴影
            text-align: center;
            display: none;//隐藏二维码
            z-index: 2;
          }
        }
        .download:hover .down-box {
          display: block;
        }
        .down-box b {
          position: absolute;
          left: 50%;
          margin-left: -9px;
          @include bgImg(21px, 21px, "/imgs/sjx.png");
          top: -13px;
        }
        .down-box img {
          width: 88px;
          height: 88px;
          display: block;
          margin: 0 auto;
        }
        a.download i {
          font-size: 14px;
          font-style: normal;
          color: #333333;
        }
      }
      .topbar-user {
        height: 40px;
        display: inline-flex;
        float: right;
        .user { // 当前登录用户信息
          display: inline-block;
          height: 40px;
          width: 90px;
          position: relative;
          text-align: center;
          margin-right: 17px;
          .user-tit {
            line-height: 40px;
            color: #b0b0b0;
            display: block;
          }
          ul {
            display: none;
            position: absolute;
            top: 40px;
            width: 90px;
            padding: 10px 0;
            z-index: 11;
            background-color: #fff;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.15);
            li {
              line-height: 30px;
              padding: 2px 0;
            }
            li:hover {
              background-color: #f5f5f5;
            }
          }
          ul a {
            display: block;
            color: #333333;
          }
          a:hover {
            color: #ff6700;
          }
        }
        .user:hover {
          background-color: #fff;
          ul {
            display: block;
            padding: 3px 0px;
            li {
              text-align: center;
            }
          }
          .user-tit {
            color: #ff6700;
          }
        }
        .log { // 登录和购物车
          display: inline-block;
          height: 40px;
          position: relative;
          text-align: center;
          top: 0;
          a {
            display: inline-block;
            position: relative;
            color: #b0b0b0;
            margin-right: 17px;
            text-decoration: none;
          }
          a:hover {
            color: #fff;
          }
          .cart {
            position: relative;
            height: 40px;
            float: right;
            margin-left: 20px;
            text-align: center;
            .my-cart {
              width: 110px;
              height: 40px;
              color: #b0b0b0;
              background-color: #666666;
              text-align: center;
              margin-right: 0;
              .icon-cart {
                @include bgImg(16px, 12px, "/imgs/icon-cart-checked.png");
                margin-right: 4px;
              }
            }
            .my-cart:hover {
              color: #ff6600;
              background-color: #fff;
              .icon-cart {
                @include bgImg(16px, 12px, "/imgs/icon-cart-hover.png");
              }
            }
            .children {
              position: absolute;
              display: none;
              width: 332px;
              height: 100px;
              line-height: 100px;
              right: 0;
              text-align: center;
              color: #424242;
              background-color: #fff;
              box-shadow: 0px 2px 10px rgba(0, 0, 0, 0.15);
              font-size: 14px;
              z-index: 10;
            }
          }
          .cart:hover {
            .children {
              display: block;
            }
          }
        }
      }
    }
  }
  .nav-header {
    .container {
      position: relative;
      height: 100px;
      @include flex();
      .header-logo{
        border-radius: 18px;
      }
      .header-menu {
        display: inline-block;
        width: 850px;
        height: 100px;
        padding-left: 180px;
        .item-menu {
          display: inline-block;
          color: #333333;
          font-weight: normal;
          font-size: 16px;
          line-height: 100px;
          margin-right: 20px;
          span {
            cursor: pointer;
          }
          &:hover {
            color: $colorA;
            .children {
              height: 220px;
              opacity: 1;
            }
          }
          .children {
            //  下拉菜单
            position: absolute;
            top: 100px;
            left: 0;
            width: 1226px;
            height: 0;
            opacity: 0;
            overflow: hidden;
            border-top: 1px solid #e5e5e5;
            box-shadow: 0px 7px 6px 0px rgba(0, 0, 0, 0.11);
            z-index: 10;
            transition: all 0.5s;
            background-color: #ffffff;
            .product {
              position: relative;
              float: left;
              width: 16.6%;
              height: 220px;
              font-size: 12px;
              line-height: 12px;
              text-align: center;
              a {
                display: inline-block;
              }
              img {
                width: auto;
                height: 111px;
                margin-top: 26px;
              }
              .pro-img {
                height: 137px;
              }
              .pro-name {
                font-weight: normal;
                margin-top: 19px;
                margin-bottom: 8px;
                color: $colorB;
              }
              .pro-price {
                color: $colorA;
              }
              &:before {
                content: " ";
                position: absolute;
                top: 28px;
                right: 0;
                border-left: 1px solid $colorF;
                height: 100px;
                width: 1px;
              }
              &:last-child:before {
                display: none;
              }
            }
          }
        }
      }
      .header-search { //   搜索框
        float: right;
        width: 296px;
        height: 50px;
        display: block;  
        // border: 0px solid #e0e0e0;
        .search-form{
          position: relative;
          width: 296px;
          height: 50px;
          z-index: 5;
          display: block;
          .hide{
            display: none !important;
            cursor: default;
          }
          .msq{
            width: 246px;
            overflow: hidden;
            .search-text{
              position: relative;
              display: inline-block;
              border: 1px solid #e0e0e0;
              border-right: 0px solid #e0e0e0;
              z-index: 1;
              width: 246px;
              height: 50px;
              line-height: 50px;
              padding: 0 10px;
            }
            .search-text:hover{
              border-color: #b0b0b0;
            }     
          }
          .search-btn{
            position: absolute;
            display: inline-block;
            z-index: 1;
            width: 48px;
            height: 48px;
            font-size: 24px;
            line-height: 24px;
            border: 1px solid #e0e0e0;
            cursor: pointer;
            a{
              @include bgImg(20px, 20px, "/imgs/icon-search.png");
              margin-left: 12px;
              margin-top: 12px;
            }
            :hover{
              @include bgImg(20px, 20px, "/imgs/icon-search1.png");
              color: #fff;
            }
          }
          .search-btn:hover{
            background-color: #ff6700;
          }
          .hotwords{
            display: block;
            position: absolute;
            top: 14px;
            right: 62px;
            z-index: 2;
            text-align: right;
          }
        }
      }
    }
  }
}
</style>