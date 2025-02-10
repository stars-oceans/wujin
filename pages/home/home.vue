<template>
  <view class="index tn-safe-area-inset-bottom">
    <!-- 顶部自定义导航 -->
    <view class="tn-flex tn-flex-row-between tn-flex-col-center tn-margin-top">
      <view class="justify-content-item tn-margin-left" @click="tn('')">
        <view class="tn-text-bold tn-text-lg tn-padding-bottom-xs">
          宁波中渠五金制品有限公司
        </view>
        <b style="font-size: 24rpx; color: #000 !important;">批发电话: <span style="color: red;" @click="phone">176XXXXXXXX</span></b>  <br>

        <view class="tn-text-xs tn-color-cat" style="opacity: 0.5;">
          <b>主营:</b> 电脑支架、电视机支架、 电视机配件
        </view>
       
        <view class="tn-text-xs tn-color-cat" style="opacity: 0.5;">
        </view>
      </view>
      <view class="justify-content-item tn-color-cat tn-text-right">
        <tn-button backgroundColor="#F1C68E00" fontColor="#838383" padding="10rpx 0" width="110rpx" shadow open-type="share">
          <!-- <text class="tn-icon-wechat-fill tn-text-xl"></text> -->
        </tn-button>
      </view>
    </view>
    
    <swiper class="card-swiper" @click="tn('')" :circular="true"
      :autoplay="true" duration="500" interval="8000" @change="cardSwiper"> 
      <swiper-item v-for="(item,index) in swiperList" :key="index" :class="cardCur==index?'cur':''">
        <view class="swiper-item image-banner" :style="'background-image:url('+ item.url + ');background-size: cover;border-radius: 15rpx;'">
        </view>
        <view class="swiper-item-text">
          <!-- <view class="tn-text-bold tn-color-white" style="font-size: 50rpx; color:">{{item.title}}</view>
          <view class="tn-color-white tn-padding-top" style="position: relative; top: -10rpx; font-size: 30rpx; height: 60rpx; z-index: 999999 !important; "><span style="display: block; height: 90rpx; z-index: 999999 !important;">{{item.name}}</span></view>
          <view class="tn-text-sm tn-text-bold tn-color-white tn-padding-top-sm tn-padding-bottom-sm">{{item.text}}</view> -->
        </view>
      </swiper-item>
    </swiper>
    <view class="indication">
        <block v-for="(item,index) in swiperList" :key="index">
            <view class="spot" :class="cardCur==index?'active':''"></view>
        </block>
    </view>
    
    <view class="tn-padding-bottom-lg">
      <view class="tn-flex tn-flex-row-between" @click="tn('')">
        <view class="justify-content-item tn-margin tn-text-bold tn-text-xxl">
          精选产品
        </view>
        <!-- <view class="justify-content-item tn-margin tn-text-lg tn-color-cat">
          <text class="tn-padding-xs">全部</text>
          <text class="tn-icon-topics"></text>
        </view> -->
      </view>
      
      <view class="tn-flex tn-margin-left tn-margin-right tn-margin-top-sm">
        <view class="tn-flex-2">
          <view class="image-pic tn-margin-right" style="background-image:url('https://cbu01.alicdn.com/img/ibank/O1CN01C1u0pL1oQM48JcbBb_!!2214181785219-0-cib.jpg')" @click="tn('')">
            <view class="image-tuniao1">
            </view>
          </view> 
        </view>
        <view class="tn-flex-1">
          <view class="image-pic" style="background-image:url('https://cbu01.alicdn.com/img/ibank/O1CN01xQAm6W1oQM4HFJbl6_!!2214181785219-0-cib.jpg')" @click="tn('')">
            <view class="image-tuniao2">
            </view>
          </view> 
          <view class="image-pic" style="background-image:url('https://cbu01.alicdn.com/img/ibank/O1CN01VO3dCF1oQLsVAItZl_!!2214181785219-0-cib.jpg');margin-top: 29rpx;" @click="tn('')">
            <view class="image-tuniao2">
            </view>
          </view> 
        </view>
      </view>
      
      
      <view class="tn-flex tn-flex-row-between tn-margin-top" @click="tn('')">
        <view class="justify-content-item tn-margin tn-text-bold tn-text-xxl">
          更多产品
        </view>
        <!-- <view class="justify-content-item tn-margin tn-text-lg tn-color-cat">
          <text class="tn-padding-xs">全部</text>
          <text class="tn-icon-topics"></text>
        </view> -->
      </view>
      <!-- 图文 -->
      <view class="tn-flex tn-flex-direction-column">
        <block v-for="(item,index) in content" :key="index">
          <view class="tn-blogger-content__wrap" @click="tn('')">
                <view class="" style="height: 600rpx;">
              <image 
                class="tn-blogger-content__main-image tn-margin-bottom-xs"
                :src="item.mainImage"
                style="display: block; margin: 0 auto; width: 100%; height: 600rpx;"
              ></image>
            </view>
            <view class="tn-blogger-content__label tn-text-justify">
              <text class="tn-blogger-content__label__desc tn-text-lg tn-text-bold tn-color-cat">{{ item.desc }}</text>  
            </view>
            
            <view class="tn-flex tn-flex-row-between tn-flex-col-center tn-margin-top-xs">
              <view class="justify-content-item tn-flex tn-flex-col-center">
                <view style="margin-right: 10rpx;margin-left: 0rpx;">
                  <view class="tn-color-gray">
                    <!-- <text class="tn-blogger-content__count-icon tn-icon-flower"></text> 
                    <text class="tn-padding-right">{{ item.collectionCount }}</text>
                    <text class="tn-blogger-content__count-icon tn-icon-message"></text>
                    <text class="tn-padding-right">{{ item.commentCount }}</text>
                    <text class="tn-blogger-content__count-icon tn-icon-like"></text>
                    <text class="">{{ item.likeCount }}</text> -->
                  </view>
                </view>
              </view>
              <view class="justify-content-item tn-text-center">
                <view v-for="(label_item,label_index) in item.label" :key="label_index" class="tn-blogger-content__label__item tn-float-left">
                  <text class="tn-blogger-content__label__item--prefix tn-icon-topics-fill"></text> {{ label_item }}
                </view>
              </view>
            </view>
          </view>
          
        </block>
      </view>
      
    </view>

    <view class='tn-tabbar-height'></view>
    
  </view>
</template>

<script>
  export default {
    name: 'Index',
    data(){
      return {
        cardCur: 0,
        isAndroid: true,
        swiperList: [{
          id: 0,
          type: 'image',
          title: '简约商务',
          name: '更多彩蛋等你探索',
          url: 'https://cbu01.alicdn.com/img/ibank/O1CN01yZVRWN1oQLsZqbAWH_!!2214181785219-0-cib.jpg',
        }, {
          id: 1,
          type: 'image',
          title: '合作勾搭',
          name: '作者微信 xxxxxxxxxxxx',
          url: 'https://cbu01.alicdn.com/img/ibank/O1CN01nG1IhX1oQLsazQ22J_!!2214181785219-0-cib.jpg',
        }, {
          id: 2,
          type: 'image',
          title: '海量分享',
          name: '总有你想不到的创意',
          url: 'https://cbu01.alicdn.com/img/ibank/O1CN01hXGdw21oQLsbPdpGA_!!2214181785219-0-cib.jpg',
        }, {
          id: 3,
          type: 'image',
          title: '酷炫多彩',
          name: '更多彩蛋等你探索',
          url: 'https://cbu01.alicdn.com/img/ibank/O1CN01CM7RBr1oQLsZqoKJW_!!2214181785219-0-cib.jpg',
        }, {
          id: 4,
          type: 'image',
          title: '适配多端',
          name: 'APP、微信小程序、H5、Finclip',
          url: 'https://cbu01.alicdn.com/img/ibank/O1CN01ASBj3A1oQLse70OeC_!!2214181785219-0-cib.jpg',
        }],
        content: [
          {
            userAvatar: 'https://cbu01.alicdn.com/img/ibank/O1CN01C1u0pL1oQM48JcbBb_!!2214181785219-0-cib.jpg',
            userName: '可我会像',
            date: '2021年12月20日',
            label: ['电视支架','电视挂架'],
            desc: '宁波厂家电视挂架电视可调架电视壁挂电视支架 电视支架厂家',
            mainImage: 'https://cbu01.alicdn.com/img/ibank/O1CN01PTHU2L1oQLrwW4515_!!2214181785219-0-cib.jpg',
            viewUser: {
              latestUserAvatar: [
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_2.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_3.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_4.jpeg'},
              ],
              viewUserCount: 129
            },
            collectionCount: 236,
            commentCount: 102,
            likeCount: 168
          },
          {
            userAvatar: 'https://cbu01.alicdn.com/img/ibank/O1CN019bkRRG1oQLs6KCmYf_!!2214181785219-0-cib.jpg',
            userName: '可我会像',
            date: '2021年12月20日',
            label: ['电视机支架'],
            desc: '电视机支架 适配尺寸37“-70” 旋转调节.挂重70KG',
            mainImage: 'https://cbu01.alicdn.com/img/ibank/O1CN019bkRRG1oQLs6KCmYf_!!2214181785219-0-cib.jpg',
            viewUser: {
              latestUserAvatar: [
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_2.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_3.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_4.jpeg'},
              ],
              viewUserCount: 129
            },
            collectionCount: 265,
            commentCount: 22,
            likeCount: 62
          },
          {
            userAvatar: 'https://cbu01.alicdn.com/img/ibank/O1CN01GoQpMH1oQLrgSDegV_!!2214181785219-0-cib.jpg',
            userName: '可我会像',
            date: '2021年12月20日',
            label: ['电视支架'],
            desc: '电视支架电视挂架电视可调架电视壁挂电视支架 电视支架厂家',
            mainImage: 'https://cbu01.alicdn.com/img/ibank/O1CN01GoQpMH1oQLrgSDegV_!!2214181785219-0-cib.jpg',
            viewUser: {
              latestUserAvatar: [
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_2.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_3.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_4.jpeg'},
              ],
              viewUserCount: 129
            },
            collectionCount: 265,
            commentCount: 22,
            likeCount: 62
          },
          {
            userAvatar: 'https://cbu01.alicdn.com/img/ibank/O1CN01wMBWB21oQLsywP0L9_!!2214181785219-0-cib.jpg',
            userName: '可我会像',
            date: '2021年12月20日',
            label: ['三屏拼接','工厂液晶显示器支架臂 '],
            desc: '工厂液晶显示器支架臂 三屏拼接增高架桌面升降架多屏夹持底座',
            mainImage: 'https://cbu01.alicdn.com/img/ibank/O1CN01wMBWB21oQLsywP0L9_!!2214181785219-0-cib.jpg',
            viewUser: {
              latestUserAvatar: [
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_2.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_3.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_4.jpeg'},
              ],
              viewUserCount: 129
            },
            collectionCount: 265,
            commentCount: 22,
            likeCount: 62
          },
          {
            userAvatar: 'https://cbu01.alicdn.com/img/ibank/O1CN01defUXA1oQLsmjVSjZ_!!2214181785219-0-cib.jpg',
            userName: '可我会像',
            date: '2021年12月20日',
            label: ['桌式电视机支架'],
            desc: '桌式电视机支架 适用32-70寸电视显示屏 旋转立体式支架',
            mainImage: 'https://cbu01.alicdn.com/img/ibank/O1CN01defUXA1oQLsmjVSjZ_!!2214181785219-0-cib.jpg',
            viewUser: {
              latestUserAvatar: [
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_2.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_3.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_4.jpeg'},
              ],
              viewUserCount: 129
            },
            collectionCount: 265,
            commentCount: 22,
            likeCount: 62
          },
          {
            userAvatar: 'https://cbu01.alicdn.com/img/ibank/O1CN01T6MqV61oQLsoScQKD_!!2214181785219-0-cib.jpg',
            userName: '可我会像',
            date: '现货笔记本支架桌面液晶显示器两用电脑升降可旋转双屏支架',
            label: ['笔记本支架'],
            desc: '现货笔记本支架桌面液晶显示器两用电脑升降可旋转双屏支架',
            mainImage: 'https://cbu01.alicdn.com/img/ibank/O1CN01T6MqV61oQLsoScQKD_!!2214181785219-0-cib.jpg',
            viewUser: {
              latestUserAvatar: [
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_2.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_3.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_4.jpeg'},
              ],
              viewUserCount: 129
            },
            collectionCount: 265,
            commentCount: 22,
            likeCount: 62
          },
          {
            userAvatar: 'https://cbu01.alicdn.com/img/ibank/O1CN01asjgo81oQLsPSU8Sm_!!2214181785219-0-cib.jpg',
            userName: '可我会像',
            date: '2021年12月20日',
            label: ['跨境','三臂电视支架电视机支架'],
            desc: '跨境支架电视支架EchoShow15支架三臂电视支架电视机支架',
            mainImage: 'https://cbu01.alicdn.com/img/ibank/O1CN01asjgo81oQLsPSU8Sm_!!2214181785219-0-cib.jpg',
            viewUser: {
              latestUserAvatar: [
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_2.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_3.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_4.jpeg'},
              ],
              viewUserCount: 129
            },
            collectionCount: 265,
            commentCount: 22,
            likeCount: 62
          },
          {
            userAvatar: 'https://cbu01.alicdn.com/img/ibank/O1CN010b9Dc01oQLsjbm452_!!2214181785219-0-cib.jpg',
            userName: '可我会像',
            date: '2021年12月20日',
            label: ['电脑增高架台式'],
            desc: '电脑增高架笔记本电脑增高台金属增高家用电脑增高架台式',
            mainImage: 'https://cbu01.alicdn.com/img/ibank/O1CN010b9Dc01oQLsjbm452_!!2214181785219-0-cib.jpg',
            viewUser: {
              latestUserAvatar: [
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_2.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_3.jpeg'},
                {src: 'https://resource.tuniaokj.com/images/blogger/avatar_4.jpeg'},
              ],
              viewUserCount: 129
            },
            collectionCount: 265,
            commentCount: 22,
            likeCount: 62
          }
        ]
      }
    },
    created() {
      const systemInfo = uni.getSystemInfoSync()
      if (systemInfo.system.toLocaleLowerCase().includes('ios')) {
        this.isAndroid = false
      } else {
        this.isAndroid = true
      }
    },
    methods: {
      phone(){
        uni.makePhoneCall({
          phoneNumber: '176XXXXXXXX'
        });
      },
      // cardSwiper
      cardSwiper(e) {
        this.cardCur = e.detail.current
      },

      // 跳转
      tn(e) {
      	uni.navigateTo({
      		url: e,
      	});
      },
    }
  }
</script>

<style lang="scss" scoped>
  .index{
    max-height: 100vh;
  }
  /* 底部安全边距 start*/
  .tn-tabbar-height {
  	min-height: 120rpx;
  	height: calc(140rpx + env(safe-area-inset-bottom) / 2);
    height: calc(140rpx + constant(safe-area-inset-bottom));
  }

  /* 轮播视觉差 start */
  .card-swiper {
    height: 350rpx !important;
  }
    
  .card-swiper swiper-item {
    width: 750rpx !important;
    left: 0rpx;
    box-sizing: border-box;
    padding: 40rpx 30rpx 30rpx 30rpx;
    overflow: initial;
  }
    
  .card-swiper swiper-item .swiper-item {
    width: 100%;
    display: block;
    height: 100%;
    border-radius: 15rpx;
    transform: scale(1);
    transition: all 0.2s ease-in 0s;
    // overflow: hidden;
  }
    
  .card-swiper swiper-item.cur .swiper-item {
    transform: none;
    transition: all 0.2s ease-in 0s;
  }
    
  .card-swiper swiper-item .swiper-item-text {
    margin-top: -160rpx;
    text-align: center;
    width: 100%;
    display: block;
    height: 50%;
    border-radius: 10rpx;
    transform: translate(100rpx, -60rpx) scale(0.9, 0.9);
    transition: all 0.6s ease 0s;
    overflow: hidden;
  }
    
  .card-swiper swiper-item.cur .swiper-item-text {
    margin-top: -220rpx;
    width: 100%;
    transform: translate(0rpx, 0rpx) scale(0.9, 0.9);
    transition: all 0.6s ease 0s;
  }
  
  .image-banner{
    border: 1rpx solid #F8F7F8;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .image-banner image{
    width: 100%;
    height: 100%;
  }
  
  /* 轮播指示点 start*/
  .indication{
    z-index: 9999;
    width: 100%;
    height: 36rpx;
    position: absolute;
    display:flex;
    flex-direction:row;
    align-items:center;
    justify-content:center;
  }
  
  .spot{
    background-color: #FFFFFF;
    opacity: 0.6;
    width: 10rpx;
    height: 10rpx;
    border-radius: 20rpx;
    top: -70rpx;
    margin: 0 8rpx !important;
    position: relative;
  }
  
  .spot.active{
    opacity: 1;
    width: 30rpx;
    background-color: #FFFFFF;
  }
  

  
 /* 图标容器12 start */
 .tn-three{
     position: absolute;
     top: 50%;
     right: 50%;
     bottom: 50%;
     left: 50%;
     transform: translate(-38rpx, -20rpx) rotateX(20deg) rotateY(10deg) rotateZ(-20deg);
     text-shadow: -1rpx 2rpx 0 #f0f0f0, -2rpx 4rpx 0 #f0f0f0, -10rpx 20rpx 30rpx rgba(0, 0, 0, 0.2);
 }
 .icon12 {
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
       width: 100rpx;
       height: 100rpx;
       font-size: 60rpx;
       border-radius: 50%;
       margin-bottom: 18rpx;
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
         background-image: url(https://resource.tuniaokj.com/images/cool_bg_image/icon_bg6.png);
 
           
       }
     }
   }
 }
  
  /* 自定义导航栏内容 start */
  .custom-nav {
    height: 100%;
    
    &__back {
      margin: auto 5rpx;
      font-size: 40rpx;
      margin-right: 10rpx;
      margin-left: 30rpx;
      flex-basis: 5%;
    }
    
    &__search {
      flex-basis: 60%;
      width: 100%;
      height: 100%;
      
      &__box {
        width: 100%;
        height: 70%;
        padding: 10rpx 0;
        margin: 0 30rpx;
        border-radius: 60rpx 60rpx 0 60rpx;
        font-size: 24rpx;
      }
      
      &__icon {
        padding-right: 10rpx;
        margin-left: 20rpx;
        font-size: 30rpx;
      }
      
      &__text {
        // color: #AAAAAA;
      }
    }
  }
  .logo-image{
    width: 65rpx;
    height: 65rpx;
    position: relative;
    border: 1rpx solid #F8F7F8;
    border-radius: 50%;
  }
  .logo-pic{
    background-size: cover;
    background-repeat:no-repeat;
    // background-attachment:fixed;
    background-position:top;
    border-radius: 50%;
  }
  /* 自定义导航栏内容 end */
  

  /* 热门图片 start*/
  .image-tuniao1{
    padding: 165rpx 0rpx;
    font-size: 40rpx;
    font-weight: 300;
    position: relative;
  }
  .image-tuniao2{
    padding: 75rpx 0rpx;
    font-size: 40rpx;
    font-weight: 300;
    position: relative;
  }
  .image-tuniao3{
    padding: 90rpx 0rpx;
    font-size: 40rpx;
    font-weight: 300;
    position: relative;
  }
  .image-pic{
    border: 1rpx solid #F8F7F8;
    background-size: cover;
    background-repeat:no-repeat;
    // background-attachment:fixed;
    background-position:top;
    border-radius: 10rpx;
  }

  /* 文章内容 start*/
  .tn-blogger-content {
    &__wrap {
      margin: 30rpx;
    }
    
    &__info {
      &__btn {
        margin-right: -12rpx;
        opacity: 0.5;
      }
    }
    
    &__label {
      &__item {
        color: #1D2541;
        background-color: #F3F2F7;
        border-radius: 10rpx;
        font-size: 22rpx;
        
        padding: 5rpx 15rpx;
        margin: 5rpx 0 0 18rpx;
        
        &--prefix {
          font-size: 24rpx;
          color: #1D2541;
          padding-right: 10rpx;
        }
      }
      
      &__desc {
        line-height: 55rpx;
      }
    }
    
    &__main-image {
      border: 1rpx solid #F8F7F8;
      border-radius: 16rpx;
      
      &--1 {
        max-width: 690rpx;
        min-width: 690rpx;
        max-height: 400rpx;
        min-height: 400rpx;
      }
      
      &--2 {
        max-width: 260rpx;
        max-height: 260rpx;
      }
      
      &--3 {
        height: 212rpx;
        width: 100%;
      }
    }
    
    &__count-icon {
      font-size: 40rpx;
      padding-right: 5rpx;
    }
  }
  
  .image-wallpaper{
    padding: 160rpx 0rpx;
    font-size: 40rpx;
    font-weight: 300;
    position: relative;
  }
  .image-pic{
    background-size: cover;
    background-repeat:no-repeat;
    // background-attachment:fixed;
    background-position:top;
    border-radius: 10rpx;
  }
  /* 文章内容 end*/
  
</style>