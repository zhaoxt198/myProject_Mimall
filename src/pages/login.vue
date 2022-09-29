<template>
  <div class="login">
    <div class="index">
      <div class="sider">
        <div class="sider-banner"></div>
      </div>
      <div class="content">
        <div class="wrapper">
          <div class="layout">
            <div class="header">
              <div class="title">
                <div class="logo">
                  <a href="/#/index"><img src="/imgs/logo-mi.png" alt="" /></a>
                </div>
                小米账号
              </div>
              <div class="nav">
                <a href="javascript:;" target="_blank" class="nav-item">用户协议</a>
                <a href="javascript:;" target="_blank" class="nav-item">隐私政策</a>
                <a href="javascript:;" target="_blank" class="nav-item">帮助中心</a><span>|</span>
                <div class="language-set">
                  <a href="javascript:;" target="_blank" class="nav-item change">中文(简体)</a>
                  <div class="language-info">
                    <ul>
                      <li><a href="javascript:;" target="_blank">中文(繁體)</a></li>
                      <li><a href="javascript:;" target="_blank">English</a></li>
                    </ul>
                  </div>
                </div>
              </div>
            </div>

            <div class="container">
              <div class="login-form">
                <div class="dialog">
                  <div class="tabs-nav">
                    <div class="tabs-nav-wrap">
                      <div class="selectlist">
                        <div class="idlogin">
                          <div class="id-login" role="tab" aria-selected="true" tabindex="0">
                            <a href="javascript:;">帐号登录</a>
                          </div>
                        </div>
                        <div class="selectbar"></div>
                        <div class="imglogin">
                          <div class="img-login" role="tab" aria-selected="false" tabindex="0">
                            <a href="javascript:;">扫码登录</a>
                            <div class="imglogin-view" role="tabpanel" tabindex="-1" aria-hidden="true">
                              <h3>扫码登录 安全快捷</h3>
                              <img src="/imgs/imglogin.jpg" alt="">
                              <span>请使用小米手机/米家等小米旗下APP扫码登录</span>
                            </div>
                          </div>
                        </div>
                      </div>
                    </div>
                  </div>
                      <div class="view">
                        <div class="content">
                         <div class="idlogin-view" role="tabpanel" tabindex="0" aria-hidden="false">
                          <form class="log-info">
                            <div class="form-content">
                              <div class="username">
                                <input :type="text" placeholder="邮箱/手机号码/小米ID" v-model="username"/>
                              </div>
                              <div class="pwd">
                                <input :type="passwordShow ? 'text' : 'password'" placeholder="密码" v-model="password"/>
                              </div>
                              <div class="acceptinfo">
                                <label for="" class="accept">
                                  <span class="checkbox">
                                    <input type="checkbox" class="checkboxinput" value/>
                                    <span class="checkboxinner"></span>
                                  </span>
                                  <span>已阅读并同意小米账号<a href=""> 用户协议</a>和 <a href=""> 隐私政策</a></span>
                                </label>
                              </div>
                              <div class="btn-box">
                                <button tabindex="-1" type="submit" style="margin-top: 20px; margin-bottom: 10px"
                                  href="#" class="btn" @click="login">
                                  登录
                                </button>
                              </div>
                              <div class="tips">
                                <div class="forget">
                                  <a href="javascript:;" class="">忘记密码？</a>
                                </div>
                                <div class="reg" @click="register">
                                  <a href="/user/register" @click="register">立即注册</a>
                                </div>
                              </div>
                            </div>
                            <div class="more-login">
                              <div class="more-login-title">其他方式登录</div>
                              <div class="more-login-content">
                                <div class="more-login-list">
                                  <div class="item"><span class="icon icon1" title="支付宝登录"></span></div>
                                  <div class="item"><span class="icon icon2" title="微信登录"></span></div>
                                  <div class="item"><span class="icon icon3" title="QQ登录"></span></div>
                                  <div class="item"><span class="icon icon4" title="新浪登录"></span></div>
                                </div>
                              </div>
                            </div>
                          </form>
                        </div>
                      </div>
                    </div>
                </div>
              </div>
            </div>

            <div class="footer">
              小米公司版权所有-京ICP备10046444-京公网安备11010802020134号-京ICP证110507号
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { mapActions } from "vuex";
import { Message } from "element-ui";

export default {
  name: "login",
  // data:{} 全局声明
  data() {
    return {
      username: "",
      password: "",
      userId: "",
      passwordShow: false,
    };
  },

  methods: {
    //登录初始为 jack,密码也为jack
    login() {
      //拿到用户输入的账号密码，因为数据是双向绑定的
      let { username, password } = this;
      this.axios.post("/user/login", {
          //这里是简写，key和value一样
          username,
          password,
        })
        .then((res) => {
          //将信息存到cookie中，expires表示过期时间
          this.$cookie.set("userId", res.id, { expires: "Session" });

          //因为登录成功以后要在首页显示用户名，所以使用vuex进行管理
          // this.$store.dispatch('saveUserName',res.username);
          this.saveUserName(res.username);
          //登录成功，跳转到首页，并传递参数，来证明是从登录页面跳转到首页的
          this.$router.push({
            //name:路由名称,params:参数(优势:路由上不会显示参数地址)
            name: "index",
            //path:路由 ,query:参数
            params: {
              from: "login",
            },
          });
        });
    },
    ...mapActions(["saveUserName"]),

    //注册
    register() {
      this.axios.post("/user/register", {
          username: "admin1",
          password: "admin1",
          email: "admin1@163.com",
        })
        .then(() => {
          //this.$message.success('注册成功');
          Message.success("注册成功");
        });
    },
  }
};
</script>
<style lang="scss">
@import './../assets/scss/mixin.scss';
.login {
  box-sizing: border-box;
  .index {
    height: 100%;
    display: flex;
    position: fixed;
    .sider {
      // 侧边图片
      flex-shrink: 0;
      flex-grow: 0;
      display: block;
      .sider-banner {
        position: fixed;
        left: 0;
        background-image: url("/imgs/sider.jpg");
        width: 18%;
        height: 100%;
        background-size: cover;
        background-position: 50%;
        display: block;
      }
    }

    .content {
      flex-shrink: 1;   // 指定flex元素的收缩规则,负值无效
      flex-grow: 1;     // 规定flex-grow项在flex容器中分配剩余空间的相对比例。负值无效，默认为 0
      display: block;
      .wrapper {
        height: 100%;
        overflow: auto;
        display: block;
        .layout {
          position: relative;
          padding-bottom: 40px;
          display: block;
          height: auto;
          .header { // 顶部信息
            margin: 0;
            overflow: hidden;
            padding: 20px;
            display: block;
            .title {
              position: fixed;
              float: left;
              left: 20%;
              height: 40px;
              font-size: 25px;
              font-weight: 540;
              color: rgb(51, 51, 51);
              line-height: 40px;
              display: block;
              .logo {
                display: inline-block;
                vertical-align: top;
                img {
                  width: 40px;
                  height: 40px;
                }
              }
            }
            .nav {
              position: fixed;
              right: 0;
              float: right;
              display: block;
              .nav-item {
                margin-left: 15px;
                margin-right: 15px;
                display: inline-block;
                font-size: 16px;
                font-weight: 400;
                color: #838383;
                height: 40px;
                line-height: 40px;
              }
              a:hover{
                color: #ff6700;
              }
              .language-set{
                position: relative;
                display: inline-block;
                ul{
                  position: absolute;
                  display: none;
                  right: 15px;
                  top: 40px;
                  height: 90px;
                  border: 1px solid #fff;
                  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.15);
                  li{
                    display: block;
                    height: 30px;
                    line-height: 25px;
                    font-size: 14px;
                    text-decoration: none;
                    text-align: center;
                    padding: 10px 10px;
                    background-color: #fff;
                    a{
                      color: #838383;
                      text-decoration: none;
                    }
                  }
                  li:hover{
                    background-color: #f5f5f5;
                  }
                }
              }
              .language-set:hover{
                ul{
                  display: block;
                }
                .change{
                  color: #ff6700;
                }
              }
            }
          }
          .container { // 中间信息
            position: fixed;
            margin-top: 88px;
            left: 28%;
            display: block;
            .login-form {
              position: relative;
              display: inline-block;
              margin-left: 25%;
              width: 400px;
              text-align: left;
              border-radius: 5px;
              padding: 50px 50px;
              box-shadow: 0 20px 50px 0 rgba(0, 0, 0, 0.1);
              .dialog {
                display: flex;
                flex-direction: column;
                color: rgba(0, 0, 0, 0.85);
                font-size: 15px;
                line-height: 1.6;
                .tabs-nav { //  登录方式
                  position: relative;
                  display: flex;
                  flex: none;   //  元素会根据自身宽高来设置尺寸
                  align-items: center;
                  margin: 0 0 16px;
                  .tabs-nav-wrap {
                    position: relative;
                    display: flex;
                    flex: auto;   // 元素会根据自身的宽度与高度来确定尺寸，但会伸长并吸收 flex 容器中额外的自由空间，也会缩短自身来适应flex容器
                    align-self: stretch;
                    .selectlist {
                      position: relative;
                      display: flex;
                      height: 40px;
                      line-height: 40px;
                      .idlogin {
                        position: relative;
                        display: inline-flex;
                        align-items: center;
                        margin: 0 20px 0 0;
                        padding: 0 0 4px;
                        height: 40px;
                        line-height: 40px;
                        font-size: 14px;
                        cursor: pointer;
                        border: 0;
                        .id-login {
                          // 账号登录
                          display: block;
                          font-size: 22px;
                          font-weight: 400;
                          color: #ff5c00;
                          text-shadow: 0 0 0.25px currentColor;
                          a {
                            font-weight: 500;
                            text-decoration: none;
                            color: #383838;
                          }
                        }
                      }
                      .selectbar{  //  登录方式分割线
                        position: absolute;
                        bottom: 8px;
                        left: 45%;
                        width: 2px;
                        height: 20px;
                        line-height: 20px;
                        background-color: #ff5c00;
                        display: block;
                        border-radius: 2px;
                      }
                      .imglogin {
                        position: relative;
                        display: inline-flex;
                        align-items: center;
                        margin: 0 20px 0 0;
                        padding: 0 0 4px;
                        height: 40px;
                        line-height: 40px;
                        font-size: 14px;
                        cursor: pointer;
                        border: 0;
                        .img-login {
                          // 扫码登录
                          position: relative;
                          display: block;
                          align-items: center;
                          font-size: 22px;
                          font-weight: 400;
                          height: 40px;
                          line-height: 40px;
                          cursor: pointer;
                          outline: none;
                          a {
                            color: #bbb;
                            text-decoration: none;
                          }
                          a:hover {
                            color: #ff6600;
                            text-shadow: 0 0 0.3px currentColor;
                          }
                          .imglogin-view {
                            position: absolute;
                            flex: none;
                            outline: none;
                            width: 350px;
                            margin-left: -110px;
                            padding: 60px 30px;
                            background-color: #fff;
                            // border: 1px solid #f5f5f5;
                            display: none;//隐藏二维码
                            z-index: 3;
                            h3{
                              margin: 0 auto 30px;
                              text-align: center;
                              font-size: 21px;
                              font-weight: 545;
                              color: #333;
                              line-height: 40px;
                            }
                            img{
                              display: block;
                              width: 200px;
                              height: 200px;
                              margin-left: 80px;
                              margin-bottom: 20px;
                              border: 0;
                            }
                            span{
                              font-size: 14px;
                              margin-left: 40px;
                              color: #c0c0c0;
                              text-align: center;
                            }
                          }
                        }
                        .img-login:hover .imglogin-view{
                          display: block;
                        }
                      }
                    }
                  }
                }
                .view {   //  登录信息
                  display: block;
                  flex: auto;
                  .content{
                  display: flex;
                  .idlogin-view {
                    flex: none;
                    // width: 100%;
                    display: block;
                    .log-info { // form
                      display: block;
                      .form-content {
                        padding: 20px 2px 0;
                        display: block;
                        .username {
                          input {
                          position: relative;
                          background: #f9f9f9;
                          border-radius: 5px;
                          padding: 20px;
                          height: 60px;
                          line-height: 40px;
                          width: 100%;
                          font-size: 16px;
                          display: block;
                          border: 0px;
                         }
                        }
                        .pwd {
                          input {
                          position: relative;
                          border-radius: 5px;
                          background: #f9f9f9;
                          padding: 20px;
                          height: 60px;
                          line-height: 20px;
                          width: 100%;
                          font-size: 16px;
                          margin-top: 20px;
                          display: block;
                          border: 0px;
                        }
                        }
                      input:focus {//输入边框焦点
                        border: 1px solid #bbb;
                        border-color: #ff6900;
                      }
                      .acceptinfo {//用户协议
                        display: block;
                        font-size: 15px;
                        font-weight: 400;
                        color: #aaa;
                        margin-top: 20px;
                        line-height: 20px;
                        .accept { //label
                          display: inline-flex;
                          align-items: baseline;
                          cursor: pointer;
                          .checkbox {
                          display: inline-block;
                          position: relative;
                          top: 0.2em;
                          cursor: pointer;
                            .checkboxinput {
                              position: absolute;
                              z-index: 1;
                              cursor: pointer;
                              width: 100%;
                              height: 100%;
                              opacity: 0.2;
                            }
                            .checkboxinput:hover{
                              border-color: #ff6900;
                            }
                            .checkboxinner {
                              position: relative;
                              display: block;
                              direction: ltr;
                              width: 20px;
                              height: 20px;
                              border-radius: 4px;
                              background-size: 100% 100%;
                              background-repeat: no-repeat;
                              background-color: #f9f9f9;
                              border: 1px solid #ddd;
                            }
                          }
                          span{
                            display: inline-block;
                            margin-left: 2px;
                            margin-right: 2px;
                          a {
                            color: #333;
                          }
                          a:hover {
                            text-decoration: none;
                          }
                          }
                        }
                      }
                      .btn-box {
                        .btn {
                          position: relative;
                          display: inline-block;
                          margin: 10px auto;
                          background-color: #ff5c00;
                          text-align: center;
                          padding: 0 20px;
                          border-radius: 4px;
                          width: 100%;
                          font-size: 18px;
                          font-weight: 400;
                          height: 60px;
                          line-height: 60px;
                          cursor: pointer;
                        }
                        :hover{
                          background-color: #ff7e29;
                        }
                      }
                      .tips {
                        display: block;
                        .forget {
                          float: left;
                          display: block;
                          margin-bottom: 10px;
                          width: 48%;
                          font-size: 17px;
                          a {
                            color: #ff5c00;
                            text-decoration: none;
                            cursor: pointer;
                            outline: none;
                          }
                        }
                        .reg {
                          float: right;
                          text-align: right;
                          display: block;
                          margin-bottom: 10px;
                          width: 48%;
                          font-size: 17px;
                          a {
                            color: #ff5c00;
                            text-decoration: none;
                            cursor: pointer;
                            outline: none;
                          }
                        }
                      }
                    }
                    .more-login{
                      display: block;
                      .more-login-title{
                        text-align: center;
                        font-size: 17px;
                        font-weight: 400;
                        color: #aaa;
                        line-height: 40px;
                        display: block;
                      }
                      .more-login-content{
                        margin-top: 10px;
                        height: 46px;
                        display: block;
                        .more-login-list{
                          text-align: center;
                          width: 100%;
                          display: block;
                          .item{
                            margin: 0 12px;
                            display: inline-block;
                            width: 46px;
                            .icon{
                              margin: 0 auto;
                              border-radius: 23px;
                              cursor: pointer;
                              display: block;
                              font-size: 46px;
                              width: 46px;
                              height: 46px;
                            }
                            .icon1{
                              @include bgImg(46px,46px,'/imgs/morelogin/zfb.png');
                            }
                            .icon2{
                              @include bgImg(46px,46px,'/imgs/morelogin/wx.png');
                            }
                            .icon3{
                              @include bgImg(46px,46px,'/imgs/morelogin/QQ.png');
                            }
                            .icon4{
                              @include bgImg(46px,46px,'/imgs/morelogin/xl.png');
                            }
                          }
                        }
                      }
                    }
                    }
                  }
                  }
                }
              }
            }
          }
          .footer { // 底部信息
            position: fixed;
            left: 42%;
            overflow: hidden;
            white-space: nowrap;//连续的空白符会被合并
            display: block;
            bottom: 15px;
            padding: 0 20px;
            color: #999;
            font-size: 14px;
          }
        }
      }
    }
  }
}
</style>