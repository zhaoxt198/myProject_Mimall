<template>
  <div class="index">
    <div class="container">
      <div class="swiper-box">
        <div class="nav-menu">
          <ul class="menu-wrap">
            <li class="menu-item"><a href="">手机</a>
              <div class="children">
                <ul v-for="(item,i) in menuList" :key="i">
                  <li v-for="(sub,j) in item" :key="j">
                    <a :href="sub ? '/#/product/' + sub.id : '' ">
                      <img :src="sub ? sub.img : '/imgs/menulist/item-box-1.jpg'" alt="">
                      {{sub ? sub.name : '小米9'}}
                    </a>
                  </li>
                </ul>
              </div>
            </li>
            <li class="menu-item"><a href="">电视</a>
              <div class="children">
                <ul v-for="(item,i) in menuList" :key="i">
                  <li v-for="(sub,j) in item" :key="j">
                    <a :href="sub ? '/#/product/' + sub.id : '' ">
                      <img :src="sub ? sub.img : '/imgs/menulist/item-box-1.jpg'" alt="">
                      {{sub ? sub.name : '小米9'}}
                    </a>
                  </li>
                </ul>
              </div>
            </li>
            <li class="menu-item"><a href="">笔记本  平板</a>
              <div class="children">
                <ul v-for="(item,i) in menuList" :key="i">
                  <li v-for="(sub,j) in item" :key="j">
                    <a :href="sub ? '/#/product/' + sub.id : '' ">
                      <img :src="sub ? sub.img : '/imgs/menulist/item-box-1.jpg'" alt="">
                      {{sub ? sub.name : '小米9'}}
                    </a>
                  </li>
                </ul>
              </div>
            </li>
            <li class="menu-item"><a href="">出行  穿戴</a>
              <div class="children">
                <ul v-for="(item,i) in menuList" :key="i">
                  <li v-for="(sub,j) in item" :key="j">
                    <a :href="sub ? '/#/product/' + sub.id : '' ">
                      <img :src="sub ? sub.img : '/imgs/menulist/item-box-1.jpg'" alt="">
                      {{sub ? sub.name : '小米9'}}
                    </a>
                  </li>
                </ul>
              </div>
            </li>
            <li class="menu-item"><a href="">耳机  音箱</a>
              <div class="children">
                <ul v-for="(item,i) in menuList" :key="i">
                  <li v-for="(sub,j) in item" :key="j">
                    <a :href="sub ? '/#/product/' + sub.id : '' ">
                      <img :src="sub ? sub.img : '/imgs/menulist/item-box-1.jpg'" alt="">
                      {{sub ? sub.name : '小米9'}}
                    </a>
                  </li>
                </ul>
              </div>
            </li>
            <li class="menu-item"><a href="">家电</a>
              <div class="children">
                <ul v-for="(item,i) in menuList" :key="i">
                  <li v-for="(sub,j) in item" :key="j">
                    <a :href="sub ? '/#/product/' + sub.id : '' ">
                      <img :src="sub ? sub.img : '/imgs/menulist/item-box-1.jpg'" alt="">
                      {{sub ? sub.name : '小米9'}}
                    </a>
                  </li>
                </ul>
              </div>
            </li>
            <li class="menu-item"><a href="">智能  路由器</a>
              <div class="children">
                <ul v-for="(item,i) in menuList" :key="i">
                  <li v-for="(sub,j) in item" :key="j">
                    <a :href="sub ? '/#/product/' + sub.id : '' ">
                      <img :src="sub ? sub.img : '/imgs/menulist/item-box-1.jpg'" alt="">
                      {{sub ? sub.name : '小米9'}}
                    </a>
                  </li>
                </ul>
              </div>
            </li>
            <li class="menu-item"><a href="">电源  配件</a>
              <div class="children">
                <ul v-for="(item,i) in menuList" :key="i">
                  <li v-for="(sub,j) in item" :key="j">
                    <a :href="sub ? '/#/product/' + sub.id : '' ">
                      <img :src="sub ? sub.img : '/imgs/menulist/item-box-1.jpg'" alt="">
                      {{sub ? sub.name : '小米9'}}
                    </a>
                  </li>
                </ul>
              </div>
            </li>
            <li class="menu-item"><a href="">生活  箱包</a>
              <div class="children">
                <ul v-for="(item,i) in menuList" :key="i">
                  <li v-for="(sub,j) in item" :key="j">
                    <a :href="sub ? '/#/product/' + sub.id : '' ">
                      <img :src="sub ? sub.img : '/imgs/menulist/item-box-1.jpg'" alt="">
                      {{sub ? sub.name : '小米9'}}
                    </a>
                  </li>
                </ul>
              </div>
            </li>
          </ul>
        </div>
        <!-- 轮播图 -->
        <swiper v-bind:options="swiperOption">
          <swiper-slide v-for="(item,index) in slideList" :key="index">
            <a v-bind:href="'/#/product/'+item.id"><img :src="item.img" alt=""></a>
          </swiper-slide>
          <!-- 分页器 -->
          <div class="swiper-pagination"  slot="pagination"></div>
          <!--左箭头。如果放置在swiper外面，需要自定义样式。-->
          <div class="swiper-button-prev" slot="button-prev"></div>
          <!--右箭头。如果放置在swiper外面，需要自定义样式。-->
          <div class="swiper-button-next" slot="button-next"></div>
        </swiper>
      </div>
      <div class="ads-box">
        <div class="bot_one">
          <div><a href=""><img src="/imgs/ads/bot_1.svg"><i>保障服务</i></a></div>
          <div><a href=""><img src="/imgs/ads/bot_2.svg"><i>企业团购</i></a></div>
          <div><a href=""><img src="/imgs/ads/bot_3.svg"><i>F码通道</i></a></div>
          <div><a href=""><img src="/imgs/ads/bot_4.svg"><i>米粉卡</i></a></div>
          <div><a href=""><img src="/imgs/ads/bot_5.svg"><i>以旧换新</i></a></div>
          <div><a href=""><img src="/imgs/ads/bot_6.svg"><i>话费充值</i></a></div>
        </div>
        <div class="bot-more">
          <a class="list" :href="'/#/product/'+ item.id" v-for="(item,index) in adsList" :key="index"><img v-lazy="item.img" alt=""></a>
        </div>
      </div>
    </div>
    <div class="product-box">
        <div class="container">
          <div class="ad-banner">
            <a href="/#/product/30"><img v-lazy="'/imgs/banner-1.png'" alt=""></a>
          </div> 
          <div class="goods-content">
            <div class="goods-type">
              <div class="type"><h2>手机</h2></div>
              <div class="more"><a href="">查看更多</a></div>
            </div>
            <div class="wrapper">
              <div class="banner-left">
                <a href="/#/product/35"><img v-lazy="'/imgs/mix-alpha.jpg'" alt=""></a>
              </div>
              <div class="list-box">
                <div class="list" v-for="(arr,i) in phoneList" :key="i">
                  <div class="item" v-for="(item,j) in arr" :key="j">
                    <span :class="{'new-pro':j%2==0}">热销</span>
                    <div class="item-img">
                      <img v-lazy="item.mainImage" alt="">
                    </div>
                    <div class="item-info">
                      <h3>{{item.name}}</h3>
                      <p>{{item.subtitle}}</p>
                      <p class="price" @click="addCart(item.id)">{{item.price}}元</p>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
    </div>
    <div class="video-box">
      <div class="container">
        <div class="video-bar">
          <div class="type"><h2>视频</h2></div>
          <div class="more"><a href="">查看更多</a></div>
        </div>
        <div class="video-content">
          <ul class="video-list">
            <li class="video-item"><a href="" title="点击播放视频">
                <div class="figure-img"><img src="/imgs/video/video1.png" lazy="loaded">
                  <a href="" target="_blank"><span class="play"  @click="showSlide = 'slideDown'"><i class="iconfont-play"></i></span></a>
                  <div class="item-video">
                    <div class="video-view" v-show="showSlide">
                      <div class="overlay"></div>
                      <div class="video" v-bind:class="showSlide">
                        <span class="icon-close" @click="closeVideo"></span>
                        <video src="/imgs/video/video.mp4" muted autoplay controls="controls"></video>
                      </div>
                    </div>
                  </div>
                </div>
                <h3 class="title">2021年春季新品发布会第一场</h3></a>
            </li>
            <li class="video-item"><a href="" title="点击播放视频">
                <div class="figure-img"><img src="/imgs/video/video2.png" lazy="loaded">
                  <span class="play"><i class="iconfont-play"></i></span>
                </div>
                <h3 class="title">Redmi 10X系列发布会</h3></a>
            </li>
            <li class="video-item"><a href="" title="点击播放视频">
                <div class="figure-img"><img src="/imgs/video/video3.png" lazy="loaded">
                  <span class="play"><i class="iconfont-play"></i></span>
                </div>
                <h3 class="title">小米10 青春版 发布会</h3></a>
            </li>
            <li class="video-item"><a href="" title="点击播放视频">
                <div class="figure-img"><img src="/imgs/video/video4.png" lazy="loaded">
                  <span class="play"><i class="iconfont-play"></i></span>
                </div>
                <h3 class="title">小米10 8K手机拍大片</h3></a>
            </li>
          </ul>
        </div>
    </div>
    </div>
<!-- 加载模态框 -->
    <modal 
    title="提示" 
    sureText="查看购物车" 
    btnType="1" 
    modalType="middle"
    v-bind:showModal="showModal"
    v-on:submit="goToCart"
    v-on:cancel="showModal=false">
    <template v-slot:body>
      <p>商品添加成功！</p>
    </template>
    </modal>
    <div class="home-toolbar">
      <a href="" class="item item-image" data-settrack="true">
        <div class="icon icon1"></div>
        <span class="text">手机APP</span>
        <div class="pop-content">
          <img src="imgs/download.jpg" alt="">
          <span class="desc">扫码领取新人百元礼包</span>
        </div>
      </a>
      <a href="" class="item" data-settrack="true">
        <div class="icon icon2"></div>
        <span class="text">个人中心</span>
      </a>
      <a href="" class="item" data-settrack="true">
        <div class="icon icon3"></div>
        <span class="text">售后服务</span>
      </a>
      <a href="" class="item" data-settrack="true">
        <div class="icon icon4"></div>
        <span class="text">人工客服</span>
      </a>
      <a href="/#/cart" class="item" data-settrack="true">
        <div class="icon icon5"></div>
        <span class="text">购物车</span>
      </a>
       <!-- href =" ":默认打开的还是当前页面，会刷新一下重新打开。 -->
       <!-- href ="#":不会刷新页面，会回到页面顶部。 -->
       <!-- href ="Javascript: void(0) ":什么也不执行，从而也就形成了一个死链接，默认阻止，不进行动作 -->
      <a href="#" class="item backtop active">
        <div class="icon icon6"></div>
        <span class="text">回顶部</span>
      </a>
    </div>
  </div>
</template>
  
<script>
import './../assets/scss/base.scss'
import { swiper, swiperSlide } from 'vue-awesome-swiper'
import 'swiper/dist/css/swiper.css'
import Modal from './../components/Modal.vue'
export default {
  name:'index',
  components:{ // 注册组件
    swiper,
    swiperSlide,
    Modal
  },
  data() {
    return {
      //轮播图属性设置
      swiperOption:{ // 轮播图设置
        autoplay:true, // 自动切换
        loop:true, // 循环模式选项，相当于切换到最后一张图片时，加上一张猫腻图，不加上，会出现直接从最后一张拉拽到第一张
        // spaceBetween : 2, //两个slide的间隔
        // slidesPerView: 1, //设置slider容器能够同时显示的slides数量(carousel模式)。
        // reeMode : true, //根据惯性滑动可能不止一格且不会贴合  
        // delayTime:2000, //毫秒；切换效果持续时间（一次切换效果执行所用的时间长度）
        effect: 'fade', // slide的切换效果 "coverflow"（3d流）
        // grabCursor: true, // 该选项给Swiper用户提供小小的贴心应用，设置为true时,鼠标覆盖Swiper时指针会变成手掌形状，拖动时指针会变成抓手形状
        // centeredSlides: true, //设定为true时，active slide会居中，而不是默认状态下的居左。
        interTime:2000, //毫秒；自动运行间隔
        pagination: { // 如果需要分页器
          el: '.swiper-pagination', // 挂载的元素
          clickable:true // 点击分页器某个点，跳转到该点击的页面
        },
        navigation: { // 如果需要前进后退按钮
          prevEl: '.swiper-button-prev',  // 左按钮
          nextEl: '.swiper-button-next',  // 右按钮
        }
      },
      slideList:[ // 轮播图片列表
        {
          id:'42',
          img:'/imgs/slider/slide-1.jpg',
          name:'Redmi K50 至尊版'
        },
        {
          id:'45',
          img:'/imgs/slider/slide-2.jpg',
          name:'Xiaomi MIX Fold 2'
        },
        {
          id:'46',
          img:'/imgs/slider/slide-3.jpg',
          name:'Xiaomi 会议宝 mini'
        },
        {
          id:'42',
          img:'/imgs/slider/slide-4.jpg',
          name:'米家折叠踢脚线电暖器'
        },
        {
          id:'42',
          img:'/imgs/slider/slide-5.jpg',
          name:'Xiaomi 12'
        }
      ],
      menuList:[ // 右拉菜单列表
        [{
            id:30,
            img:'/imgs/menuList/item-box-1.jpg',
            name:'Xiaomi MIX Fold 2'
          },
          {
            id:31,
            img:'/imgs/menuList/item-box-2.jpg',
            name:'Note 11T Pro+'
          },
          {
            id:32,
            img:'/imgs/menuList/item-box-3.jpg',
            name:'Redmi 10A'
          },
          {
            id:33,
            img:'/imgs/menuList/item-box-4.jpg',
            name:'Xiaomi 12'
          }],
        [{ id: 5,
            img: "/imgs/menuList/item-box-5.jpg",
            name: "Redmi K50 至尊版",},
          { id: 6,
            img: "/imgs/menuList/item-box-6.jpg",
            name: "Note 11T Pro",},
          { id: 7,
            img: "/imgs/menuList/item-box-7.jpg",
            name: "Redmi K50 Pro",},
          { id: 8,
            img: "/imgs/menuList/item-box-8.jpg",
            name: "Xiaomi 12X",}],
        [{ id: 9,
            img: "/imgs/menuList/item-box-9.jpg",
            name: "Xiaomi 12S Ultra",},
          { id: 10,
            img: "/imgs/menuList/item-box-10.jpg",
            name: "Note 11SE",},
          { id: 11,
            img: "/imgs/menuList/item-box-11.jpg",
            name: "Redmi K50",},
          { id: 12,
            img: "/imgs/menuList/item-box-12.jpg",
            name: "Xiaomi 11青春活力版",}],
        [{ id: 13,
            img: "/imgs/menuList/item-box-13.jpg",
            name: "Xiaomi 12S Pro",},
          { id: 14,
            img: "/imgs/menuList/item-box-14.jpg",
            name: "Xiaomi Civi 1S",},
          { id: 15,
            img: "/imgs/menuList/item-box-15.jpg",
            name: "Redmi K40S",},
          { id: 16,
            img: "/imgs/menuList/item-box-16.jpg",
            name: "Note 11 Pro系列",}],
        [{ id: 17,
            img: "/imgs/menuList/item-box-17.jpg",
            name: "Xiaomi 12S",},
          { id: 18,
            img: "/imgs/menuList/item-box-18.jpg",
            name: "黑鲨5 Pro",},
          { id: 19,
            img: "/imgs/menuList/item-box-19.jpg",
            name: "Redmi K50 电竞版",},
          { id: 20,
            img: "/imgs/menuList/item-box-20.jpg",
            name: "Note 11 4G",}],
        [{ id: 21,
            img: "/imgs/menuList/item-box-21.jpg",
            name: "Xiaomi 12 Pro 天玑版",},
          { id: 22,
            img: "/imgs/menuList/item-box-22.jpg",
            name: "黑鲨5",},
          { id: 23,
            img: "/imgs/menuList/item-box-23.jpg",
            name: "Xiaomi 12 Pro",},
          { id: 24,
            img: "/imgs/menuList/item-box-24.jpg",
            name: "Note 11 5G",}],
      ],
      adsList:[ // 4列广告
        {
          id:48,
          img:'/imgs/ads/ads-2.jpg',
          name: "Xiaomi MIX Fold 2"
        },
        {
          id:45,
          img:'/imgs/ads/ads-3.jpg',
          name: "Xiaomi 12S Pro"
        },
        {
          id:47,
          img:'/imgs/ads/ads-4.jpg',
          name: "Xiaomi Watch S1"
        }
      ],
      phoneList:[],
      showModal:false,
      showSlide: "", //控制动画效果
    };
  },
  mounted() {
    this.init();
  },
  methods: {
    init(){
      this.axios.get('products',{
        params:{
          categoryId:100012,
          pageSize:14
        }
      }).then((res)=>{
        res.list = res.list.slice(6,14);
        this.phoneList = [res.list.slice(0,4),res.list.slice(4,8)];
      })
    },
    addCart(id){
      this.showModal = true;
      this.axios.post('/carts',{
        productId:id,
        selected:true
      }).then((res)=>{
        this.$store.dispatch('saveCartCount',res.cartTotalQuantity);
      }).catch(()=>{
        this.showModal = true;
      })
    },
    goToCart(){
      this.$router.push('/cart')
    },
    closeVideo() { // 关闭视频
      this.showSlide = "slideUp";
      setTimeout(() => {
        this.showSlide = "";
      }, 300);
    }
  },
  created() {
  },
}
</script>

<style lang='scss' scoped>
@import './../assets/scss/config.scss';
@import './../assets/scss/mixin.scss';
  .index{
    .swiper-box{
      width: 1226px;
      height: 460px;
      .nav-menu{
        position: absolute;
        width: 232px;
        height: 460px;
        z-index: 9;
        padding: 26px 0;
        background-color: #55585a7a;
        box-sizing: border-box;
        .menu-wrap{
          .menu-item{
            height: 45px;
            line-height: 50px;
            a{
              display: block;
              position: relative;
              font-size: 15px;
              color: #ffffff;
              padding-left: 30px;
              &:after{ // 透明右箭头
                position: absolute;
                right: 30px;
                top:17.5px;
                content: '';
                @include bgImg(10px,15px,'/imgs/icon-arrow.png')
              }
            }
            &:hover{
              background-color: $colorA;
              .children{
                display: block;
              }
            }
            .children{
              position: absolute;
              display: none;
              width: 992px;
              height: 100%;
              background-color: $colorG;
              top:0;
              left:232px;
              border:1px solid $colorH;
              ul{
                display: flex;
                justify-content: space-between;
                height: 75px;
                li{
                  height: 75px;
                  line-height: 75px;
                  flex:1;
                  padding-left: 23px;
                }
                a{
                  color: $colorB;
                  font-size: 14px;
                }
                img{
                  width: 42px;
                  height: 35px;
                  vertical-align: middle;
                  margin-right: 15px;
                }
              }       
            }  
          }
        }
      }
      .swiper-container{
        height: 460px;
        --swiper-theme-color: #ff6600; // 左右按钮
        --swiper-pagination-color: #00ff33;
        .swiper-button-prev{ // 左箭头
        position:absolute;
        top:50%;
        width:40px;
        height:30px;
        margin-top:-35px;
        z-index:10;
        cursor:pointer;
        outline:none;
        left: 234px;
        right: auto;
        // color: #d1d1d2;
        background-image: url("data:image/svg+xml;charset=utf-8,%3Csvg%20xmlns%3D'http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg'%20viewBox%3D'0%200%2027%2044'%3E%3Cpath%20d%3D'M0%2C22L22%2C0l2.1%2C2.1L4.2%2C22l19.9%2C19.9L22%2C44L0%2C22L0%2C22L0%2C22z'%20fill%3D'%23d1d1d2'%2F%3E%3C%2Fsvg%3E");
      }
      .swiper-button-next{  // 右箭头
        position:absolute;
        top:50%;
        width:40px;
        height:30px;
        margin-top:-35px;
        z-index:10;
        cursor:pointer;
        outline:none;
        right: 0;
        left: auto;
        // color: #d1d1d2;
        background-image: url("data:image/svg+xml;charset=utf-8,%3Csvg%20xmlns%3D'http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg'%20viewBox%3D'0%200%2027%2044'%3E%3Cpath%20d%3D'M27%2C22L27%2C22L5%2C44l-2.1-2.1L22.8%2C22L2.9%2C2.1L5%2C0L27%2C22L27%2C22z'%20fill%3D'%23d1d1d2'%2F%3E%3C%2Fsvg%3E");
      }
      .swiper-pagination{  // 分页器
        height: 21px;
        margin-left: -35px;
        position:absolute;
        text-align:right;
        transform:translateZ(0);
        z-index:10;
        transition-delay:0s;
        // color: #d1d1d2;
      }  
        img{
          width: 100%;
          height: 100%;
        }
      }
    } // swiper-box

    .ads-box{ // 四块广告
      @include flex();
      margin-top: 15px;
      margin-bottom: 35px;
      .bot_one{ // 6模块
        width: 234px;
        height: 170px;
        div{
          position: relative;
          display: inline-block;
          width: 76px;
          height: 83px;
          line-height: 30px;
          box-shadow: 0 1px 0 #aaa;
          border-left: 1px solid #665e57;
          border-bottom: 1px solid #665e57;
          background-color: #5f5750;
          text-align: center;
          a{
            color: #cccac7;
            cursor: pointer;
          }
          a:hover{
            color: #fff;
            text-decoration: none;
          }
          a img{
            width: 23px;
            height: 23px;
            display: block;
            margin-bottom: 5px;
            margin: 20px auto auto;
          }
          i{
            font-style: normal;
          }
        }
      }
      .bot-more{
        width: 990px;
        float: left;
        display: block;
        .list{
          width: 315px;
          height: 170px;
          margin-left: 15px;
          display: inline-block;
        }
        :hover{
          transform: scale(1.0005);
          box-shadow: 0 20px 50px 0 rgba(0, 0, 0, 0.1);
        }
      }
    }

    .product-box{ // 商品
      background-color: #f5f5f5;
      padding-top: 4px;
      padding-bottom: 12px;
      .container{
        width: 1226px;
        margin-right: auto;
        margin-left: auto;
        display: block;
        .ad-banner{ // 单栏广告
          height: 120px;
          margin: 22px 0;
          display: block;
        }
        .goods-content{
          margin-bottom: 8px;
          display: block;
        .goods-type{
          height: 58px;
          position: relative;
          .type{
            float: left;
            height: 58px;
            h2{
            font-size: 22px;
            font-weight: 200;
            line-height: 58px;
            color: #333;
            margin-bottom: 20px;
            }
          }
          .more{
            float: right;
            line-height: 41px;
            a{
              color: $colorB;
              font-size: $fontI;
              font-size: 16px;
              line-height: 58px;
              width: 25px;
              vertical-align: middle;
              cursor: pointer;
              &:after{
                @include bgImg(20px,20px,'/imgs/more.png');
                color: #ffffff;
                border-color: #fff;
                border-radius: 16px;
                background-color: #b0b0b0;
                content: "";
                margin-left: 5px;
                vertical-align: sub;
              }
            }
            a:hover{
              color: #ff6700;
              text-decoration: none;
            }
          }
        }
        .wrapper{
          display: flex;
          .banner-left{ // 左栏竖直广告
            margin-right: 16px;
            img{
              width: 224px;
              height: 619px;
            }
            :hover{
              border-radius: 2px;
              transform: scale(1.005);
              box-shadow: 0 20px 50px 0 rgba(0, 0, 0, 0.1);
            }
          }
          .list-box{
            .list{
              @include flex();//使用flex布局
              width: 986px;
              margin-bottom: 15px;
              &:last-child{
                margin-bottom: 20px;
              }
              .item{
                display: block;
                width: 236px;
                height: 302px;
                background-color: $colorG;
                text-align: center;
                span{ // 热销
                  display: inline-block;
                  width: 67px;
                  height: 24px;
                  font-size: 14px;
                  line-height: 24px;
                  color: $colorG;//fff
                  &.new-pro{  //  热销
                    background-color:#cf6868;//#7ECF68
                  }
                  &.kill-pro{
                    background-color: #e82626;//#E82626
                  }
                }
                .item-img{
                  img{
                    height: 195px;
                    width:100%
                  }
                }
                .item-info{
                  h3{
                    font-size: $fontJ;
                    color: $colorB;
                    line-height: $fontJ;
                    font-weight: bold;
                  }
                  p{
                    color:$colorD;
                    line-height: 13px;
                    margin:6px auto 13px;
                  }
                  .price{
                    color: #ff6700;
                    font-size: $fontJ;
                    font-weight: bold;
                    cursor: pointer;
                    &:after{ // 购物车图标
                      @include bgImg(22px,22px,'/imgs/icon-cart-hover.png');
                      content: "";
                      margin-left: 5px;
                      vertical-align: middle;
                    }
                  }
                }
              }
              .item:hover{
                border-radius: 5px;
                transform: scale(1.005); // 对图片进行放大
                box-shadow: 0 20px 50px 0 rgba(0, 0, 0, 0.1);
              }
            }     
          }
        }
      }
      }
    }

    .video-box{ // 视频
      background-color: #f5f5f5;
      padding-top: 4px;
      padding-bottom: 12px;
      .container{
        width: 1226px;
        margin-right: auto;
        margin-left: auto;
        display: block;
        .video-bar{
          height: 58px;
          position: relative;
          .type{
            float: left;
            height: 58px;
            h2{
            font-size: 22px;
            font-weight: 200;
            line-height: 58px;
            color: #333;
            margin-bottom: 20px;
            }
          }
          .more{
            float: right;
            line-height: 41px;
            a{
              color: $colorB;
              font-size: $fontI;
              font-size: 16px;
              line-height: 58px;
              width: 25px;
              vertical-align: middle;
              cursor: pointer;
              &:after{
                @include bgImg(20px,20px,'/imgs/more.png');
                color: #ffffff;
                border-color: #fff;
                border-radius: 16px;
                background-color: #b0b0b0;
                content: "";
                margin-left: 5px;
                vertical-align: sub;
              }
            }
            a:hover{
              color: #ff6700;
              text-decoration: none;
            }
          }
        }
        .video-content{
          display: block;
          .video-list{
            display: block;
            width: 1230px;
            height: 285px;
            .video-item{ // li
              position: relative;
              float: left;
              width: 296px;
              height: 285px;
              margin-bottom: 14px;
              text-align: center;
              display: list-item;
              margin-left: 14px;
              a{
                text-decoration: none;
                color: #757575;
                cursor: pointer;
                .figure-img{
                  position: relative;
                  height: 180px;
                  margin: 0 0 28px;
                  display: block;
                  img{
                    width: 296px;
                    height: 180px;
                    border: 0;
                  }
                  .play{
                    position: absolute;
                    left: 20px;
                    bottom: 10px;
                    width: 32px;
                    height: 20px;
                    border: 2px solid #fff;
                    border-radius: 12px;
                    i{ @include bgImg(20px, 20px,'/imgs/video/play.png')}
                  }
                  // .video-view{
                  //   .overlay {
                  //     @include position(fixed);
                  //     background-color: #333333;
                  //     opacity: 0.4;
                  //     z-index: 10;
                  //   }
                  //   @keyframes slideDown {
                  //     from {
                  //       top: -50%;
                  //       opacity: 0;
                  //     }
                  //     to {
                  //       top: 50%;
                  //       opacity: 1;
                  //     }
                  //   }
                  //   @keyframes slideUp {
                  //     from {
                  //       top: 50%;
                  //       opacity: 1;
                  //     }
                  //     to {
                  //       top: -50%;
                  //       opacity: 0;
                  //     }
                  //   }
                  //   .video {
                  //     position: fixed;
                  //     top: -50%;
                  //     left: 50%;
                  //     transform: translate(-50%, -50%);
                  //     z-index: 10;
                  //     width: 1400px;
                  //     height: 836px;
                  //     opacity: 1;
                  //     &.slideDown {
                  //       animation: slideDown 0.6s linear;
                  //       top: 50%;
                  //     }
                  //     &.slideUp {
                  //       animation: slideUp 0.6s linear;
                  //     }
                  //     .icon-close {
                  //       position: absolute;
                  //       top: 20px;
                  //       right: 20px;
                  //       @include bgImg(30px, 30px, '/imgs/icon-close.png');
                  //       cursor: pointer;
                  //       z-index: 11;
                  //     }
                  //     video {
                  //       width: 90%;
                  //       height: 90%;
                  //       object-fit: cover;//被替换的内容在保持其宽高比的同时填充元素的整个内容框。
                  //       outline: none;
                  //     }
                  //   }
                  // }
                }
                .title{
                  font-size: 14px;
                  font-weight: 400;
                  color: #333;
                }
                .figure-img:hover{
                  .play{
                    background-color: #ff6700;
                  }
                }
              }
            }
            .video-item:first-child{
              margin-left: 0;
            }
            .video-item:hover{
              border-radius: 5px;
              transform: scale(1.005); // 对图片进行放大
              box-shadow: 0 20px 50px 0 rgba(0, 0, 0, 0.1);
            }
          }
        }
      }
    }
  }
  .index .home-toolbar{
    position: fixed;
    right: 0;
    bottom: 70px;
    z-index: 99;
    display: block;
    .item{
      position: relative;
      display: block;
      width: 82px;
      height: 90px;
      margin-top: -1px;
      text-decoration: none;
      background-color: #fff;
      border: 1px solid #f5f5f5;
      text-align: center;
      .icon{
        position: relative;
        width: 30px;
        height: 30px;
        margin: 0 auto 8px;
        padding-top: 18px;
        display: block;
      } 
      .icon1:before{
        @include bgImg(30px,30px,'/imgs/hometool/app.png');
        content: "";
      }
      .icon2:before{
        @include bgImg(30px,30px,'/imgs/hometool/person.png');
        content: "";
      }
      .icon3:before{
        @include bgImg(30px,30px,'/imgs/hometool/service.png');
        content: "";
      }
      .icon4:before{
        @include bgImg(30px,30px,'/imgs/hometool/contact.png');
        content: "";
      }
      .icon5:before{
        @include bgImg(30px,30px,'/imgs/hometool/cart.png');
        content: "";
      }
      .icon6:before{
        @include bgImg(30px,30px,'/imgs/hometool/backtop.png');
        content: "";
      }
      .icon1:hover:before{
        @include bgImg(30px,30px,'/imgs/hometool/app1.png');
      }
      .icon2:hover:before{
        @include bgImg(30px,30px,'/imgs/hometool/person1.png');
      }
      .icon3:hover:before{
        @include bgImg(30px,30px,'/imgs/hometool/service1.png');
      }
      .icon4:hover:before{
        @include bgImg(30px,30px,'/imgs/hometool/contact1.png');
      }
      .icon5:hover:before{
        @include bgImg(30px,30px,'/imgs/hometool/cart1.png');
      }
      .icon6:hover:before{
        @include bgImg(30px,30px,'/imgs/hometool/backtop1.png');
      }
      .text{
        color: #757575;
      }
      .text:hover{
        color: #ff6700;
      }
      .pop-content{
        position: absolute;
        right: 83px;
        top: 0;
        padding: 14px;
        background-color: #fff;
        border: 1px solid #f5f5f5;
        box-shadow: 0 1px 1px #aaa;//图片阴影
        text-align: center;
        display: none;//隐藏二维码
        z-index: 2;
        img{
          display: block;
          width: 90px;
          height: 90px;
          margin: 6px auto;
          border: 0;
        }
        .desc{
          display: block;
          width: 82px;
          font-size: 14px;
          margin: 14px auto 0;
          text-align: center;
          color: #757575;
        }
      }
      .backtop{
        margin-top: 14px;
        border-top: 1px solid #f5f5f5;
      }
      .backtop.active{
        visibility: visible;
      }
    }
    .item-image:hover .pop-content{
      display: block;
    }
  }
</style>