<template>
  <div class="footer">
      <div class="wrap">
          <div class="contact">
              <div class="title">我们的联系方式</div>
              <div class="phone">
                  <img src="@/assets/image/phone-iocn.png" alt="电话">
                  <span class="text">{{info.contactMobile}}</span>
              </div>
              <div class="e-mail">
                  <img src="@/assets/image/el-icon.png" alt="邮箱">
                  <span class="text">{{info.email}}</span>
              </div>
              <div class="address">
                  <img src="@/assets/image/adress-icon.png" alt="地址">
                  <span class="text">{{info.address}}</span>
              </div>
          </div>
          <div class="navs">
              <div class="title">快捷导航</div>
              <div class="item">
                <div class="items text"  v-for="(item,index) in nav" :key='index' @click="link(item)">{{item.title}}</div>
              </div>
          </div>
          <div class="gzh">
              <div class="title">其他平台</div>
              <div class="img"><img class="pic" src="@/assets/image/rightNav/code1.png" alt=""></div>
          </div>
      </div>
      <div class="bottom">
          <div>©2019-2023 广州xxxxxx有限公司 </div>
          <div>浙ICP备12002384号-4</div>
          <div>xxxxx有限公司版权所有</div>
      </div>
  </div>
</template>

<script>
export default {
    data () {
        return {
            nav: [
                { title: '关于我们', path: '/aboutUs' },
                { title: '专利服务', path: '/ptServe' },
                { title: '商标服务', path: '/tmServe' },
                { title: '版权服务', path: '/copyrightServe' },
                { title: '项目服务', path: '/projectServe' },
                { title: '联系我们', path: '/callMe' }
            ]
        }
    },
    props: {
        info: {
            type: Object,
            default () {
                return {}
            }
        }
    },
    methods: {
        link (item) {
            this.$router.push({ path: item.path })
        }
    }
}
</script>

<style lang='scss' scoped>
.footer{
    height: 300px;
    width: 100%;
    background-color: #222;
    color: #fff;
    padding-top: 30px;
    .wrap{
        width: 1200px;
        margin: 0 auto;
        display: flex;
        .text{
            opacity: .6;
        }
        > div {
            .title{
                font-size: 20px;
                padding-bottom: 40px;
            }
        }
        .contact{
            width: 250px;
            padding-right: 100px;
            div {
                display: flex;
                align-items: center;
                img{
                    padding-right: 10px;
                }
            }
            .phone, .e-mail, .address{
                line-height: 27px;
                font-weight: 400;
                padding-bottom: 12px;
            }
        }
        .navs{
            width: 500px;
            padding-right: 100px;
            .item{
                display: flex;
                flex-wrap: wrap;
            }
            .items{
                padding: 0 50px 32px 0;
                font-size: 16px;
                cursor: pointer;
            }
        }
        .gzh{
            .pic{
                width: 128px;
                height: 128px;
            }
        }
        .address{
            flex: 1;
        }
    }
    .bottom{
        width: 1200px;
        line-height: 45px;
        margin: 0 auto;
        margin-top: 40px;
        border-top: 1px solid rgb(121, 116, 116);
        display: flex;
        justify-content: space-around;
        > div{
            color: #fff;
            opacity: .3;
        }
    }
}
</style>
