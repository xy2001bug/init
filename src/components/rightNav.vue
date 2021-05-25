<template>
  <div class="nav">
      <div class="static">
          <div style="height:174px" @click="handerShowPop"><img src="@/assets/image/rightNav/zixun.png" class="zixun" alt=""></div>
          <div class="img_bg active">
              <img class="phone_moren" src="@/assets/image/rightNav/phone_moren.png" alt="">
              <img class="phone_hover" src="@/assets/image/rightNav/rightnavPhone.png" alt="">
              <div class="contact">
                  服务热线： {{ info.contactMobile }}
              </div>
          </div>
          <div class="img_bg active">
              <img class="phone_moren" src="@/assets/image/rightNav/gzh_moren.png" alt="">
              <img class="phone_hover" src="@/assets/image/rightNav/right_codeicon.png" alt="">
              <div class="contact contact_code">
                  <img class="code_pic" src="../assets/image/rightNav/code1.png" alt="">
              </div>
          </div>
          <!-- <div class="img_bg">
              <img src="@/assets/image/rightNav/right_top.png" alt="">
          </div> -->
      </div>
  </div>
</template>

<script>
export default {
    data () {
        return {}
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
        handerShowPop () {
            this.$emit('show')
        }
    }
}
</script>

<style lang='scss' scoped>
.nav{
    height: 300px;
    .static{
        display: flex;
        flex-direction: column;
        align-items: center;
        .zixun{
            height: 183px;
            width: 81px;
            padding-right: 2px;
            cursor: pointer;
        }
        img{
            display: block;
        }
        .img_bg{
            height: 42px;
            width: 42px;
            border-radius: 4px;
            background: #fff;
            margin-bottom: 5px;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            cursor: pointer;
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
            .phone_hover{
                display: none;
            }
            .contact{
                position: absolute;
                width: 281px;
                height: 60px;
                right: 100%;
                background: url('../assets/image/rightNav/contact.png') no-repeat;
                background-size: 100% 100%;
                text-align: center;
                line-height: 60px;
                color: #F28723;
                display: none;
            }
            .contact_code{
                height: 178px;
                width: 178px;
                background: url('../assets/image/rightNav/code_bg.png');
                right: 130%;
                .code_pic{
                    width: 148px;
                    height: 148px;
                    padding: 12px 10px 10px 15px;
                }
            }
            &:hover{
                background-color: #F28723;
            }
        }
        .active:hover{
            .phone_moren{
                display: none;
            }
            .contact{
                display: block;
            }
            .phone_hover{
                display: block;
            }
        }
    }
}
</style>
