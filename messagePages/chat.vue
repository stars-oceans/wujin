<template>
  <view class="template-content">
    <!-- 顶部自定义导航 -->
    <tn-nav-bar fixed alpha customBack>
      <view slot="back" class='tn-custom-nav-bar__back'
        @click="goBack">
        <text class='icon tn-icon-left'></text>
        <text class='icon tn-icon-home-capsule-fill'></text>
      </view>
    </tn-nav-bar>
    
    
    
    <view class="" :style="{paddingTop: vuex_custom_bar_height + 'px'}">
      
      <view class="tn-text-justify">
        
        <view class="tn-margin">
          <view class="tn-flex tn-flex-row-between tn-flex-col-center">
            <view class="justify-content-item">
              <view class="tn-flex tn-flex-col-top tn-flex-row-left">
                <view class="logo-pic tn-shadow-blur tn-margin-top-sm" style="background-image:url('https://resource.tuniaokj.com/images/blogger/blogger_beibei.jpg')">
                  <view class="logo-image" >
                  </view>
                </view>
                <view class="tn-padding-right tn-color-black">
                  
                  <view class="tn-padding-left-sm tn-text-bold tn-margin-top-sm" style="max-width: 62vw;">
                    图鸟_北北
                  </view>
                  <view class="tn-flex tn-flex-col-center">
                    <view class="tn-bg-gray--light tn-margin-sm tn-padding-sm" style="max-width: 62vw;border-radius: 0 15rpx 15rpx 15rpx;">
                      <text class="">???? 下午去抓猪</text>
                    </view>
                    <view class="">
                      <!-- 发送失败 -->
                      <!-- <text class="tn-icon-warning-fill tn-color-purplered tn-text-xxl"></text> -->
                    </view>
                  </view>
                  
                </view>
                
              </view>
            </view>
            <view class="justify-content-item">
              <!-- 预留空位 -->
            </view>
          </view>
        </view>
        
        <view class="tn-margin">
          <view class="tn-flex tn-flex-row-between tn-flex-col-center">
            <view class="justify-content-item">
              <view class="tn-flex tn-flex-col-top tn-flex-row-left">
                <view class="logo-pic tn-shadow-blur tn-margin-top-sm" style="background-image:url('https://resource.tuniaokj.com/images/blogger/blogger_beibei.jpg')">
                  <view class="logo-image" >
                  </view>
                </view>
                <view class="tn-padding-right tn-color-black">
                  
                  <view class="tn-padding-left-sm tn-text-bold tn-margin-top-sm" style="max-width: 62vw;">
                    图鸟_北北
                  </view>
                  <view class="tn-flex tn-flex-col-center">
                    <view class="tn-margin-sm" style="max-width: 62vw;">
                      
                      <view class="bg-img-cont tn-shadow-blur"
                        style="background-image:url('https://resource.tuniaokj.com/images/content/rodion.jpg');">
                      </view>
                      
                    </view>
                    <view class="">
                      <!-- 发送失败 -->
                      <!-- <text class="tn-icon-warning-fill tn-color-purplered tn-text-xxl"></text> -->
                    </view>
                  </view>
                  
                </view>
                
              </view>
            </view>
            <view class="justify-content-item">
              <!-- 预留空位 -->
            </view>
          </view>
        </view>
        
        <view class="tn-margin">
          <view class="tn-flex tn-flex-row-between tn-flex-col-center">
            <view class="justify-content-item">
              <view class="tn-flex tn-flex-col-top tn-flex-row-left">
                <view class="logo-pic tn-shadow-blur tn-margin-top-sm" style="background-image:url('https://resource.tuniaokj.com/images/blogger/blogger_beibei.jpg')">
                  <view class="logo-image" >
                  </view>
                </view>
                <view class="tn-padding-right tn-color-black">
                  
                  <view class="tn-padding-left-sm tn-text-bold tn-margin-top-sm" style="max-width: 62vw;">
                    图鸟_北北
                  </view>
                  <view class="tn-flex tn-flex-col-center">
                    <view class="tn-bg-gray--light tn-margin-sm tn-padding-sm" style="max-width: 62vw;border-radius: 0 15rpx 15rpx 15rpx;">
                      <text class="">地址：广东省广州市番禺区祈福新村129号</text>
                    </view>
                    <view class="">
                      <text class="tn-icon-location-fill tn-color-blue tn-text-xxl"></text>
                    </view>
                  </view>
                  
                </view>
                
              </view>
            </view>
            <view class="justify-content-item">
              <!-- 预留空位 -->
            </view>
          </view>
        </view>
        
        
        <view class="tn-margin">
          <view class="tn-flex tn-flex-row-between tn-flex-col-center">
            <view class="justify-content-item">
              <!-- 预留空位 -->
            </view>
            <view class="justify-content-item">
              <view class="tn-flex tn-flex-col-top tn-flex-row-left">
                
                <view class="tn-padding-left tn-color-black">
                  <view class="tn-padding-right tn-text-bold tn-margin-top-sm tn-text-right" style="max-width: 62vw;">
                    图鸟_东东
                  </view>
                  <view class="tn-flex tn-flex-col-center">
                    <view class="">
                      <!-- 发送失败 -->
                      <text class="tn-icon-warning-fill tn-color-purplered tn-text-xxl"></text>
                    </view>
                    <view class="tn-bg-gray--light tn-margin-sm tn-padding-sm" style="max-width: 62vw;border-radius: 15rpx 0 15rpx 15rpx;">
                      <text class="">遵命北北大人</text>
                    </view>
                  </view>
                </view>
                <view class="logo-pic tn-shadow-blur tn-margin-top-sm" style="background-image:url('https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg')">
                  <view class="logo-image" >
                  </view>
                </view>
                
              </view>
            </view>
          </view>
        </view>
        
        
        <view class="tn-text-center">
          <text class="tn-bg-gray--light tn-text-xs" style="border-radius: 6rpx;padding: 10rpx 14rpx;">晚上7:02</text>
        </view>
        
        <view class="tn-margin">
          <view class="tn-flex tn-flex-row-between tn-flex-col-center">
            <view class="justify-content-item">
              <!-- 预留空位 -->
            </view>
            <view class="justify-content-item">
              <view class="tn-flex tn-flex-col-top tn-flex-row-left">
                
                <view class="tn-padding-left tn-color-black">
                  <view class="tn-padding-right tn-text-bold tn-margin-top-sm tn-text-right" style="max-width: 62vw;">
                    图鸟_东东
                  </view>
                  <view class="tn-flex tn-flex-col-center">
                    <view class="">
                      <!-- 发送失败 -->
                      <!-- <text class="tn-icon-warning-fill tn-color-purplered tn-text-xxl"></text> -->
                    </view>
                    <view class="tn-bg-gray--light tn-margin-sm tn-padding-sm" style="max-width: 62vw;border-radius: 15rpx 0 15rpx 15rpx;">
                      <text class="">现在就去抓</text>
                    </view>
                  </view>
                </view>
                <view class="logo-pic tn-shadow-blur tn-margin-top-sm" style="background-image:url('https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg')">
                  <view class="logo-image" >
                  </view>
                </view>
                
              </view>
            </view>
          </view>
        </view>
        
        <view class="tn-margin">
          <view class="tn-flex tn-flex-row-between tn-flex-col-center">
            <view class="justify-content-item">
              <view class="tn-flex tn-flex-col-top tn-flex-row-left">
                <view class="logo-pic tn-shadow-blur tn-margin-top-sm" style="background-image:url('https://resource.tuniaokj.com/images/blogger/blogger_beibei.jpg')">
                  <view class="logo-image" >
                  </view>
                </view>
                <view class="tn-padding-right tn-color-black">
                  
                  <view class="tn-padding-left-sm tn-text-bold tn-margin-top-sm" style="max-width: 62vw;">
                    图鸟_北北
                  </view>
                  <view class="tn-flex tn-flex-col-center">
                    <view class="tn-bg-gray--light tn-margin-sm tn-padding-sm" style="max-width: 62vw;border-radius: 0 15rpx 15rpx 15rpx;">
                      <text class="">你开玩笑吗，现在在几点了</text>
                    </view>
                    <!-- <view class="">
                      <text class="tn-icon-location-fill tn-color-blue tn-text-xxl"></text>
                    </view> -->
                  </view>
                  
                </view>
                
              </view>
            </view>
            <view class="justify-content-item">
              <!-- 预留空位 -->
            </view>
          </view>
        </view>
        
        
        <view class="tn-margin">
          <view class="tn-flex tn-flex-row-between tn-flex-col-center">
            <view class="justify-content-item">
              <!-- 预留空位 -->
            </view>
            <view class="justify-content-item">
              <view class="tn-flex tn-flex-col-top tn-flex-row-left">
                
                <view class="tn-padding-left tn-color-black">
                  <view class="tn-padding-right tn-text-bold tn-margin-top-sm tn-text-right" style="max-width: 62vw;">
                    图鸟_东东
                  </view>
                  <view class="tn-flex tn-flex-col-center">
                    <view class="">
                      <!-- 发送失败 -->
                      <!-- <text class="tn-icon-warning-fill tn-color-purplered tn-text-xxl"></text> -->
                    </view>
                    <view class="tn-bg-gray--light tn-margin-sm tn-padding-sm" style="max-width: 62vw;border-radius: 15rpx 0 15rpx 15rpx;">
                      <text class="">可以的，我点蜡烛</text>
                    </view>
                  </view>
                </view>
                <view class="logo-pic tn-shadow-blur tn-margin-top-sm" style="background-image:url('https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg')">
                  <view class="logo-image" >
                  </view>
                </view>
                
              </view>
            </view>
          </view>
        </view>
        
        <view class="tn-margin">
          <view class="tn-flex tn-flex-row-between tn-flex-col-center">
            <view class="justify-content-item">
              <view class="tn-flex tn-flex-col-top tn-flex-row-left">
                <view class="logo-pic tn-shadow-blur tn-margin-top-sm" style="background-image:url('https://resource.tuniaokj.com/images/blogger/blogger_beibei.jpg')">
                  <view class="logo-image" >
                  </view>
                </view>
                <view class="tn-padding-right tn-color-black">
                  
                  <view class="tn-padding-left-sm tn-text-bold tn-margin-top-sm" style="max-width: 62vw;">
                    图鸟_北北
                  </view>
                  <view class="tn-flex tn-flex-col-center">
                    <view class="tn-bg-gray--light tn-margin-sm tn-padding-sm" style="max-width: 62vw;border-radius: 0 15rpx 15rpx 15rpx;">
                      <text class="">那就赶紧去，早去早回</text>
                    </view>
                    <!-- <view class="">
                      <text class="tn-icon-location-fill tn-color-blue tn-text-xxl"></text>
                    </view> -->
                  </view>
                  
                </view>
                
              </view>
            </view>
            <view class="justify-content-item">
              <!-- 预留空位 -->
            </view>
          </view>
        </view>
        
        
        <view class="tn-margin">
          <view class="tn-flex tn-flex-row-between tn-flex-col-center">
            <view class="justify-content-item">
              <!-- 预留空位 -->
            </view>
            <view class="justify-content-item">
              <view class="tn-flex tn-flex-col-top tn-flex-row-left">
                
                <view class="tn-padding-left tn-color-black">
                  <view class="tn-padding-right tn-text-bold tn-margin-top-sm tn-text-right" style="max-width: 62vw;">
                    图鸟_东东
                  </view>
                  <view class="tn-flex tn-flex-col-center">
                    <view class="">
                      <!-- 发送失败 -->
                      <!-- <text class="tn-icon-warning-fill tn-color-purplered tn-text-xxl"></text> -->
                    </view>
                    <view class="tn-bg-gray--light tn-margin-sm tn-padding-sm" style="max-width: 62vw;border-radius: 15rpx 0 15rpx 15rpx;">
                      <text class="">遵命大人，此处发送爱心</text>
                    </view>
                  </view>
                </view>
                <view class="logo-pic tn-shadow-blur tn-margin-top-sm" style="background-image:url('https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg')">
                  <view class="logo-image" >
                  </view>
                </view>
                
              </view>
            </view>
          </view>
        </view>
        

        
      </view>
      
    </view>
    
    
    <view class="tabbar footerfixed tn-bg-white">
      <view class="tn-flex tn-flex-row-between tn-flex-col-center">
        <view class="justify-content-item tn-margin-top">
          <view class="tn-flex tn-flex-row-center tn-flex-col-center">
            
            
            <!-- <view class="tn-flex tn-flex-row-center tn-padding-right tn-padding-left">
              <text class="tn-icon-emoji-good tn-text-xxl"></text>
            </view> -->
            
            <view class="tn-flex tn-flex-row-center tn-flex-col-center tn-padding-right tn-padding-left-sm">
              <view class="icon27__item--icon tn-flex tn-flex-row-center tn-flex-col-center tn-shadow-blur" style="background-color: #F3F2F7;color: #7C8191;">
                <view class="tn-icon-panda"></view>
              </view>
              <!-- <view class="avatar-all">
                <view class="tn-shadow-blur" style="background-image:url('https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg');width: 60rpx;height: 60rpx;background-size: cover;">
                </view>
              </view> -->
            </view>
            
            
            <view class="topic__info__item__input tn-flex tn-flex-direction-row tn-flex-nowrap tn-flex-col-center tn-flex-row-left ">
              <!-- <view class="topic__info__item__input__left-icon">
                <view class="tn-icon-emoji-good"></view>
              </view> -->
              <view class="topic__info__item__input__content">
                <input maxlength="20" placeholder-class="input-placeholder" placeholder=" " :cursor-spacing="18" />
              </view>
            </view>
            
    
            
          </view>
        </view>
        <view class="justify-content-item tn-flex-row-center tn-flex-col-center tn-margin-top tn-margin-right">
          <view class="topic__info__item__sure">
            <view class="tn-flex-1 justify-content-item tn-text-center">
              <tn-button shape="round" backgroundColor="#1D2541" width="100%" shadow>
                <text class="tn-color-white" hover-class="tn-hover" :hover-stay-time="150">
                  发 送
                </text>
              </tn-button>
            </view>
          </view>
        </view>
      </view>
    </view>
    
    
    <view class='tn-tabbar-height'></view>
    
  </view>
</template>

<script>
  import template_page_mixin from '@/libs/mixin/template_page_mixin.js'
  export default {
    name: 'TemplateContent',
    mixins: [template_page_mixin],
    data(){
      return {}
    },
    methods: {
      
    }
  }
</script>

<style lang="scss" scoped>
  /* 胶囊*/
  .tn-custom-nav-bar__back {
    width: 100%;
    height: 100%;
    position: relative;
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    box-sizing: border-box;
    background-color: rgba(0, 0, 0, 0.15);
    border-radius: 1000rpx;
    border: 1rpx solid rgba(255, 255, 255, 0.5);
    color: #FFFFFF;
    font-size: 18px;
    
    .icon {
      display: block;
      flex: 1;
      margin: auto;
      text-align: center;
    }
    
    &:before {
      content: " ";
      width: 1rpx;
      height: 110%;
      position: absolute;
      top: 22.5%;
      left: 0;
      right: 0;
      margin: auto;
      transform: scale(0.5);
      transform-origin: 0 0;
      pointer-events: none;
      box-sizing: border-box;
      opacity: 0.7;
      background-color: #FFFFFF;
    }
  }
  .tn-tabbar-height {
  	min-height: 100rpx;
  	height: calc(120rpx + env(safe-area-inset-bottom) / 2);
  }
  
  /* 用户头像 start */
  .logo-image {
    width: 80rpx;
    height: 80rpx;
    position: relative;
  }
  
  .logo-pic {
    background-size: cover;
    background-repeat: no-repeat;
    // background-attachment:fixed;
    background-position: top;
    // box-shadow: 0rpx 0rpx 80rpx 0rpx rgba(0, 0, 0, 0.15);
    border-radius: 50%;
    // overflow: hidden;
    // background-color: #FFFFFF;
  }
  
  .bg-img-cont {
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    height: 260rpx;
    width: 55vw;
    margin: 10rpx 0 0 0;
    border-radius: 12rpx;
  }
  
  /* 图标容器27 start */
  .icon27 {
    &__item {
      width: 30%;
      background-color: #FFFFFF;
      border-radius: 10rpx;
      padding: 30rpx;
      margin: 20rpx 10rpx;
      transform: scale(1);
      transition: transform 0.3s linear;
      transform-origin: center center;
      
      &--icon {
        width: 70rpx;
        height: 70rpx;
        font-size: 50rpx;
        border-radius: 50%;
        position: relative;
        z-index: 1;
        
        &::after {
          content: " ";
          position: absolute;
          z-index: -1;
          width: 100%;
          height: 100%;
          left: 0;
          bottom: 0;
          border-radius: inherit;
          opacity: 1;
          transform: scale(1, 1);
          background-size: 100% 100%;
  
            
        }
      }
    }
  }
  
  
  /* 底部 start*/
  .footerfixed{
   position: fixed;
   width: 100%;
   bottom: 0;
   z-index: 999;
   background-color: rgba(255,255,255,0.5);
   box-shadow: 0rpx 0rpx 30rpx 0rpx rgba(0, 0, 0, 0.07);
  }
  
  .tabbar {
    align-items: center;
    min-height: 130rpx;
  	padding: 0;
  	height: calc(130rpx + env(safe-area-inset-bottom) / 2);
  	padding-bottom: calc(30rpx + env(safe-area-inset-bottom) / 2);
    padding-left: 10rpx;
    padding-right: 10rpx;
  }
  
  /* 头像*/
  .avatar-all {
    width: 60rpx;
    height: 60rpx;
    border: 4rpx solid rgba(255,255,255,0.05);
    border-radius: 50%;
    overflow: hidden;
    box-shadow: 0rpx 0rpx 80rpx 0rpx rgba(0, 0, 0, 0.15);
  }
  
  /* 内容*/
  .topic {
    position: relative;
    height: 100%;
    z-index: 1;
    margin-bottom: 120rpx;
    
    
    /* 表单信息 start */
    &__info {
      margin: 0 50rpx;
      margin-top: 105rpx;
      padding: 30rpx 51rpx;
      border-radius: 20rpx;
      background-color: rgba(255,255,255,1);
      border: 2rpx solid rgba(255, 255, 255, 0.1);
      box-shadow: 0rpx 10rpx 50rpx 0rpx rgba(0, 3, 72, 0.1);
      
      &__item {
        
        &__input {
          width: 400rpx;
          height: 60rpx;
          background-color: rgba(0, 3, 72, 0.05);
          border-radius: 10rpx;
          
          &__left-icon {
            width: 10%;
            font-size: 44rpx;
            margin-left: 20rpx;
            margin-right: 5rpx;
            color: #C6D1D8;
          }
          
          &__content {
            width: 80%;
            padding-top: 0rpx;
            padding-left: 30rpx;
            
            &--verify-code {
              width: 56%;
            }
            
            input {
              font-size: 35rpx;
              color: #1D2541;
              // letter-spacing: 0.1em;
            }
          }
          
          &__right-icon {
            width: 10%;
            font-size: 34rpx;
            margin-right: 20rpx;
            color: #78909C;
          }
          
          &__right-verify-code {
            width: 34%;
            margin-right: 20rpx;
          }
        }
        
        &__button {
          width: 100%;
          height: 60rpx;
          text-align: center;
          font-size: 31rpx;
          font-weight: bold;
          line-height: 77rpx;
          // text-indent: 1em;
          border-radius: 100rpx;
          color: #FFFFFF;
          background-color: rgba(255,255,255,0.2);
          // border: 2rpx solid #FFFFFF;
        }
        
        &__sure {
          height: 60rpx;
          width: 140rpx;
        }
        
      }
    }
    /* 表单信息 end */
    
    /* 内容 end */
    
  }
  
  /deep/.input-placeholder {
    font-size: 30rpx;
    color: #7C8191;
  }
  
</style>
