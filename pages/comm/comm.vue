<template>
  <view class="circle tn-safe-area-inset-bottom bg">

      <view class="tn-margin-top-sm"style="margin-top: 230rpx;" :style="{paddingTop: vuex_custom_bar_height + 'px'}" @click="tn('')">
        <view class="tn-flex tn-flex-row-between tn-round tn-padding-xs tn-margin he" style="border: 1rpx solid #D6D1F0;background: linear-gradient(-160deg, #F1F7FF, #DEE6FF, #F3F8FF, #D0DBFF);">
            <view class="tn-text-bold">
              电话:134XXXXXXXXX
            </view>
        </view>
      </view>
      <view class="tn-margin-top-sm" style="margin-top: 50rpx;" @click="tn('')">
        <view class="tn-flex tn-flex-row-between tn-round tn-padding-xs tn-margin he" style="border: 1rpx solid #D6D1F0;background: linear-gradient(-160deg, #F1F7FF, #DEE6FF, #F3F8FF, #D0DBFF);">
            <view class="tn-text-bold">
              微信:134XXXXXXXXX
            </view>
        </view>
      </view>
     
      <view class="tn-margin-top-sm" style="margin-top: 50rpx;" @click="tn('')">
        <view class="tn-flex tn-flex-row-between tn-round tn-padding-xs tn-margin he" style="border: 1rpx solid #D6D1F0;background: linear-gradient(-160deg, #F1F7FF, #DEE6FF, #F3F8FF, #D0DBFF);">
            <view class="tn-text-bold">
              地址:浙江省宁波市鄞州区，XXXX
            </view>
        </view>
      </view>

      <view class="tn-margin-top-sm" style="margin-top: 50rpx;" @click="tn('')">
        <view class="tn-flex tn-flex-row-between tn-round tn-padding-xs tn-margin he" style="border: 1rpx solid #D6D1F0;background: linear-gradient(-160deg, #F1F7FF, #DEE6FF, #F3F8FF, #D0DBFF);">
            <view class="tn-text-bold">
            邮箱: 123@qq.com
            </view>
        </view>
      </view>
  </view>
</template>

<script>
  export default {
    name: 'Circle',
    data(){
      return {
          cardCur: 0,
          adAutoplay: false,
          
          /* 压屏窗*/
          show2: false,
          maskCloseable: true,
      }
    },
    onLoad() {
      this.initContentData()
      this.contentHideShowHeight = uni.upx2px(56) * 3
    },
    onReady() {
      // this.$nextTick(() => {
      //   this.getContentRectInfo()
      // })
    },
    onShow() {
      this.adAutoplay = true
    },
    onHide() {
      this.adAutoplay = false
    },
    methods: {
      // cardSwiper
      cardSwiper(e) {
        this.cardCur = e.detail.current
        for (let i = 0; i < this.swiperList.length; i++) {
          const videoContext = uni.createVideoContext(`video-${this.swiperList[i]['id']}`, this)
          if (i === this.cardCur) {
            // #ifdef H5
            videoContext.play()
            // #endif
            // #ifndef H5
            videoContext.play()
            // #endif
            
          } else {
            // #ifdef MP-WEIXIN
            videoContext.stop()
            // #endif
            // #ifndef MP-WEIXIN
            videoContext.pause()
            // #endif
          }
        }
      },
      // 暂停所有视频
      stopAllVideo() {
        this.current = 0
      },
      // tab选项卡切换
      tabChange(index) {
        this.current = index
      },
      // 跳转
      tn(e) {
      	uni.navigateTo({
      		url: e,
      	});
      },
      // 震动跳转
      navEdit(e) {
        wx.vibrateLong();
        uni.navigateTo({
          url: '/circlePages/edit'
        })
      },
      // 震动跳转
      navCreate(e) {
        wx.vibrateLong();
        uni.navigateTo({
          url: '/circlePages/create'
        })
      },
      // 震动跳转
      navBuild(e) {
        wx.vibrateLong();
        uni.navigateTo({
          url: '/circlePages/build'
        })
      },
      // 处理内容，给内容添加对应的标识信息
      initContentData() {
        this.content.forEach((item, index) => {
          // 是否需要隐藏内容
          item.hideContent = false
          // 显示所有内容
          item.showAllContent = false
          // 内容容器的实际高度
          item.contentContainerHeight = 0
          // 内容容器是否初始化完成
          item.contentContainerInit = false
          this.$set(this.content, index, item)
        })
      },
      // 获取内容容器的信息
      getContentRectInfo() {
        let contentRect = {}
        const query = uni.createSelectorQuery().in(this)
        // 筛选出存在内容的数据
        this.content.forEach((item, index) => {
          if (item?.content) {
            query.select(`#blogger__content--${index}`).boundingClientRect()
            contentRect[index] = item
          }
        })
        // 获取所有内容的宽高信息
        query.exec(res => {
          if (!res) {
            setTimeout(() => {
              this.getContentRectInfo()
            }, 10)
            return
          }
          // console.log(res);
          res.map((item) => {
            // console.log(item.height, this.contentHideShowHeight);
            // 获取对应的标号
            const id = item.id
            const idIndex = /blogger__content--(\d)/.exec(id)[1]
            let contentItem = this.content[idIndex]
            contentItem.hideContent = item.height > this.contentHideShowHeight
            contentItem.showAllContent = false
            contentItem.contentContainerHeight = item.height
            contentItem.contentContainerInit = true
            this.$set(this.content, idIndex, contentItem)
            
            // console.log(/blogger__content--(\d)/.exec(id)[1]);
          })
        })
      },
      // 切换内容的显示与隐藏
      switchContentShowStatus(index) {
        const contentItem = this.content[index]
        contentItem.showAllContent = !contentItem.showAllContent
        this.$set(this.content, index, contentItem)
      },
      
      // 弹出压屏窗
      showLandscape() {
        this.openLandscape()
      },
      // 打开压屏窗
      openLandscape() {
        // wx.vibrateLong();
        this.show2 = true
      },
      // 关闭压屏窗
      closeLandscape() {
        this.show2 = false
      }
    }
  }
</script>

<style lang="scss" scoped>
.bg{
  width: 100vw;
  height: 100vh;
  background: url('../bg.jpg') no-repeat;
overflow: hidden;
background-size: cover;
background-position: -300rpx 0;
}
.he{
  height: 100rpx;
  display: flex;
  align-items: center;
  justify-content: center;
}
	.circle{
	  max-height: 100vh;
	}
  /* 底部安全边距 start*/
  .tn-tabbar-height {
  	min-height: 120rpx;
  	height: calc(140rpx + env(safe-area-inset-bottom) / 2);
    height: calc(140rpx + constant(safe-area-inset-bottom));
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
        color: #AAAAAA;
      }
    }
  }
  .logo-image{
    width: 60rpx;
    height: 60rpx;
    position: relative;
    margin-top: -15rpx;
  }
  .logo-pic{
    background-size: cover;
    background-repeat:no-repeat;
    // background-attachment:fixed;
    background-position:top;
    border-radius: 50%;
  }
  /* 自定义导航栏内容 end */
  /* 博主头像 start*/
  .image-circle{
    // padding: 95rpx;
    width: 190rpx;
    height: 190rpx;
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
  
  .tn-color-cat{
    color: #1D2541;
  }
  .tn-bg-cat{
    background-color: #1D2541;
  }
  
/* 文章内容 start*/
  .blogger {
    &__item {
      padding: 30rpx;
    }
    
    &__author {
      &__btn {
        margin-right: -12rpx;
        opacity: 0.5;
      }
    }
    
    &__desc {
      line-height: 30rpx;
      
      &__label {
        
        color: #1D2541;
        background-color: #F3F2F7;
        border-radius: 10rpx;
        font-size: 22rpx;
        
        padding: 5rpx 15rpx;
        margin: 5rpx 18rpx 0 0;
        
        &--prefix {
          font-size: 24rpx;
          color: #1D2541;
          padding-right: 10rpx;
        }
      }
      &__content {
        line-height: 50rpx;
      }
    }
    
    &__content {
      margin-top: 18rpx;
      padding-right: 18rpx;
      
      &__data {
        line-height: 46rpx;
        text-align: justify;
        overflow: hidden;
        transition: all 0.25s ease-in-out;

      }
      
      &__status {
        margin-top: 10rpx;
        font-size: 26rpx;
        color: #82B2FF;
      }
    }
    
    &__main-image {
      border: 1rpx solid #F8F7F8;
      border-radius: 16rpx;
      
      &--1 {
        max-width: 80%;
        max-height: 300rpx;
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
    
    &__ad {
      width: 100%;
      height: 500rpx;
      transform: translate3d(0px, 0px, 0px) !important;
      
      ::v-deep .uni-swiper-slide-frame {
        transform: translate3d(0px, 0px, 0px) !important;
      }
      .uni-swiper-slide-frame {
        transform: translate3d(0px, 0px, 0px) !important;
      }
      
      &__item {
        position: absolute;
        width: 100%;
        height: 100%;
        transform-origin: left center;
        transform: translate3d(100%, 0px, 0px) scale(1) !important;
        transition: transform 0.25s ease-in-out;
        z-index: 1;
        
        &--0 {
          transform: translate3d(0%, 0px, 0px) scale(1) !important;
          z-index: 4;
        }
        &--1 {
          transform: translate3d(13%, 0px, 0px) scale(0.9) !important;
          z-index: 3;
        }
        &--2 {
          transform: translate3d(26%, 0px, 0px) scale(0.8) !important;
          z-index: 2;
        }
      }
      
      &__content {
        border-radius: 40rpx;
        width: 640rpx;
        height: 500rpx;
        overflow: hidden;
      }
      
      &__image {
        width: 100%;
        height: 100%;
      }
    }
  }
  /* 文章内容 end*/
   
   /* 间隔线 start*/
  .tn-strip-bottom {
   width: 100%;
   border-bottom: 20rpx solid rgba(241, 241, 241, 0.8);
  }
   /* 间隔线 end*/
  
  /* 广告内容 start */
  .ad-image{
    width: 80rpx;
    height: 80rpx;
    position: relative;
  }
  .ad-pic{
    background-size: cover;
    background-repeat:no-repeat;
    // background-attachment:fixed;
    background-position:top;
    border-radius: 20%;
  }
  /* 自定义导航栏内容 end */
  
  
  /* 全屏轮播  start*/
  .card-swiper {
    height: 100vh !important;
  }
    
  .card-swiper swiper-item {
    width: 750rpx !important;
    left: 0rpx;
    box-sizing: border-box;
    overflow: initial;
  }
    
  .card-swiper swiper-item .swiper-item {
    width: 100%;
    display: block;
    height: 100vh;
    border-radius: 0rpx;
    transform: scale(1);
    transition: all 0.2s ease-in 0s;
    overflow: hidden;
  }
    
  .card-swiper swiper-item.cur .swiper-item {
    transform: none;
    transition: all 0.2s ease-in 0s;
  }
    
  .card-swiper swiper-item .swiper-item-png {
    margin-top: -50vh;
    width: 100%;
    display: block;
    border-radius: 0rpx;
    transform: translate(1040rpx, 20rpx) scale(0.5, 0.5);
    transition: all 0.6s ease 0s;
    // overflow: hidden;
  }
    
  .card-swiper swiper-item.cur .swiper-item-png {
    margin-top: -100vh;
    width: 900rpx;
    transform: translate(-80rpx, 0rpx) scale(1, 1);
    transition: all 0.6s ease 0s;
  }
  .image-banner{
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .image-banner image{
    width: 100%;
  }
  
  /* 轮播指示点 start*/
  .indication{
    z-index: 9999;
    width: 100%;
    height: 36rpx;
    position: fixed;
    // display:flex;
    display: block;
    flex-direction:row;
    align-items:center;
    justify-content:center;
  }
  
  .spot{
    background-color: #000;
    opacity: 0.3;
    width: 10rpx;
    height: 10rpx;
    border-radius: 20rpx;
    margin: 20rpx 0 !important;
    left: 95vw;
    top: -60vh;
    position: relative;
  }
  
  .spot.active{
    opacity: 0.6;
    height: 30rpx;
    background-color: #000;
  }  
  
  /* 资讯主图 start*/
  .image-article {
    border-radius: 8rpx;
    border: 1rpx solid #F8F7F8;
    width: 200rpx;
    height: 200rpx;
    position: relative;
  }
  
  .image-pic {
    background-size: cover;
    background-repeat: no-repeat;
    // background-attachment:fixed;
    background-position: top;
    border-radius: 10rpx;
  }
  
  .article-shadow {
    border-radius: 15rpx;
    box-shadow: 0rpx 0rpx 50rpx 0rpx rgba(0, 0, 0, 0.07);
  }
  
  /* 文字截取*/
  .clamp-text-1 {
    -webkit-line-clamp: 1;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    text-overflow: ellipsis;
    overflow: hidden;
  }
  
  .clamp-text-2 {
    -webkit-line-clamp: 2;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    text-overflow: ellipsis;
    overflow: hidden;
  }
  
  /* 标签内容 start*/
  .tn-tag-content {
    &__item {
      display: inline-block;
      line-height: 35rpx;
      color: #1D2541;
      background-color: #F3F2F7;
      border-radius: 10rpx;
      font-size: 22rpx;
      padding: 5rpx 15rpx;
  
      &--prefix {
        padding-right: 10rpx;
      }
    }
  }
  
  
  /* 图标容器9 start */
  .icon9 {
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
        width: 110rpx;
        height: 110rpx;
        font-size: 65rpx;
        border-radius: 50%;
        margin: 20rpx 40rpx;
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
          background-image: url(https://resource.tuniaokj.com/images/cool_bg_image/icon_bg5.png);
        }
      }
    }
  }
  
  
  /* 悬浮 */
  .tnxuanfu{
    animation: suspension 3s ease-in-out infinite;
  }
  
  @keyframes suspension {
    0%, 100% {
      transform: translateY(0);
    }
    50% {
      transform: translateY(-0.8rem);
    }
  }
  /* 悬浮按钮 */
  .button-shop {
    width: 90rpx;
    height: 90rpx;
    display: flex;
    flex-direction: row;
    position: fixed;
    /* bottom:200rpx;
      right: 20rpx; */
    left: 5rpx;
    top: 5rpx;
    z-index: 1001;
    border-radius: 100px;
    opacity: 0.9;
  }
  
  
  /* 按钮 */
  .edit {
    bottom: 300rpx;
    right: 75rpx;
    position: fixed;
    z-index: 9999;
  }
  
  
  .pa,
  .pa0 {
    position: absolute
  }
  
  .pa0 {
    left: 0;
    top: 0
  }
  
  
  .bg0 {
    width: 100rpx;
    height: 100rpx;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
  
  .bg1 {
    width: 100%;
    height: 100%;
  }
  
  
  
  
  .hx-box {
    top: 50%;
    left: 50%;
    width: 100rpx;
    height: 100rpx;
    transform-style: preserve-3d;
    transform: translate(-50%, -50%) rotateY(75deg) rotateZ(10deg);
  }
  
  .hx-box .pr {
    width: 100rpx;
    height: 100rpx;
    transform-style: preserve-3d;
    animation: hxz 20s linear infinite;
  }
  
  @keyframes hxz {
    0% {
      transform: rotateX(0deg);
    }
  
    100% {
      transform: rotateX(-360deg);
    }
  }
  
  
  
  .hx-box .pr .pa0 {
    width: 100rpx;
    height: 100rpx;
    /* border: 4px solid #5ec0ff; */
    border-radius: 1000px;
  }
  
  .hx-box .pr .pa0 .span {
    display: block;
    width: 100%;
    height: 100%;
    background: url(https://resource.tuniaokj.com/images/cool_bg_image/arc4.png) no-repeat center center;
    background-size: 100% 100%;
    animation: hx 4s linear infinite;
  }
  
  @keyframes hx {
    to {
      transform: rotate(360deg);
    }
  }
  
  .hx-k1 {
    transform: rotateX(-60deg) rotateZ(-60deg)
  }
  
  .hx-k2 {
    transform: rotateX(-30deg) rotateZ(-30deg)
  }
  
  .hx-k3 {
    transform: rotateX(0deg) rotateZ(0deg)
  }
  
  .hx-k4 {
    transform: rotateX(30deg) rotateZ(30deg)
  }
  
  .hx-k5 {
    transform: rotateX(60deg) rotateZ(60deg)
  }
  
  .hx-k6 {
    transform: rotateX(90deg) rotateZ(90deg)
  }
 
</style>
