<template>
  <div class="service">
    <ul class="list-service">
      <li>
        <a href=""><span class="icon-setting"></span>预约维修服务</a>
      </li>
      <li>
        <a href=""><span class="icon-7day"></span>7天无理由退货</a>
      </li>
      <li>
        <a href=""><span class="icon-15day"></span>15天免费换货</a>
      </li>
      <li>
        <a href=""><span class="icon-post"></span>满69元包邮</a>
      </li>
      <li>
        <a href=""><span class="icon-service"></span>1100余家售后网点</a>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "service-bar",
};
</script>
<style lang="scss">
@import "./../assets/scss/mixin.scss";
.service {
  display: block;
  padding: 27px 0;
  border-bottom: 1px solid #e0e0e0;
  color: #666666;
  .list-service {
    // ul
    display: block;
    margin: 0;
    padding: 0;
    list-style-type: none;
    height: 25px;
    line-height: 25px;
    li:first-child {
      border-left: 0;
    }
    li {
      float: left;
      display: list-item;
      font-size: 16px;
      width: 19.8%;
      list-style: none;
      text-align: center;
      border-left: 1px solid #e0e0e0;
      a {
        color: #616161;
        cursor: pointer;
        span {
          display: inline-block;
          width: 20px;
          height: 20px;
          vertical-align: middle;
          margin-right: 8px;
        }
        .icon-setting {
          @include bgImg(20px, 20px, "/imgs/service/icon-setting.png");
        }
        .icon-7day {
          @include bgImg(20px, 20px, "/imgs/service/icon-7day.png");
        }
        .icon-15day {
          @include bgImg(20px, 20px, "/imgs/service/icon-15day.png");
        }
        .icon-post {
          @include bgImg(20px, 20px, "/imgs/service/icon-post.png");
        }
        .icon-service {
          @include bgImg(20px, 20px, "/imgs/service/icon-loc.png");
        }
      }
      a:hover {
        text-decoration: none;
        color: #ff6700;
      }
    }
  }
}
</style>