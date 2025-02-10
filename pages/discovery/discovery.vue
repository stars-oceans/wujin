<template>
  <view class="discovery tn-safe-area-inset-bottom">
    <swiper
      class="card-swiper"
      @click="tn('')"
      :circular="true"
      :autoplay="false"
      duration="500"
      interval="8000"
      @change="cardSwiper"
    >
      <swiper-item
        v-for="(item, index) in swiperList"
        :key="index"
        :class="cardCur == index ? 'cur' : ''"
      >
        <view class="swiper-item image-banner">
          <image
            :src="item.url"
            mode="aspectFill"
            v-if="item.type == 'image'"
          ></image>
        </view>

        <view class="swiper-item-text">
          <view class="tn-padding swiper-item-title">
            <view
              class="tn-text-bold tn-color-white"
              style="font-size: 40rpx"
              >{{ item.title }}</view
            >
            <view
              class="tn-color-white tn-padding-top"
              style="font-size: 25rpx"
              >{{ item.name }}</view
            >
          </view>
        </view>
      </swiper-item>
    </swiper>
    <view class="indication">
      <block v-for="(item, index) in swiperList" :key="index">
        <view class="spot" :class="cardCur == index ? 'active' : ''"></view>
      </block>
    </view>

    <view class="tn-margin-top-sm">
      <tn-sticky :offsetTop="0" :customNavHeight="vuex_custom_bar_height">
        <tn-tabs
          :list="fixedList"
          :current="current"
          :isScroll="true"
          activeColor="#000"
          :bold="true"
          :fontSize="32"
          :badgeOffset="[20, 50]"
          @change="tabChange"
          backgroundColor="#FFFFFF99"
          :height="110"
        ></tn-tabs>
      </tn-sticky>
    </view>
    <view class="content_box">
          <div class="item_box" v-for="(item, index) in list" :key="index">
              <div class="item__image":style="{ backgroundImage: `url(${item.mainImage})` }" :src="item.mainImage">
              </div>
              <div class="item__data">
                <div class="item__title-container">
                  <div class="item__title">{{ item.title }}</div>
                </div>
                <div class="item__tags container">
                  <div class="item__tags
                    tag" v-for="(tag, index) in item.tags" :key="index">
                    {{ tag }}
                  </div>
                  </div>
                  </div>
                  </div>  
    </view>
  </view>
</template>

<script>
import template_page_mixin from "@/libs/mixin/template_page_mixin.js";
export default {
  name: "Discovery",
  mixins: [template_page_mixin],
  data() {
    return {
      cardCur: 0,
      swiperList: [
        {
          id: 0,
          type: "image",
          title: "笔记本电脑托盘桌面支架",
          name: "笔记本电脑托盘桌面支架笔记本支架显示器支架笔记本托支架",
          url: "https://cbu01.alicdn.com/img/ibank/O1CN01ITfGNg1oQM2Cu0y1c_!!2214181785219-0-cib.310x310.jpg",
        },
        {
          id: 1,
          type: "image",
          title: "跨境电商增高架",
          name: "跨境电商增高架台式电脑增高架笔记本电脑增高台显示器增高架承重",
          url: "https://cbu01.alicdn.com/img/ibank/O1CN01ZL4Q3Y1oQM29fQ3m7_!!2214181785219-0-cib.jpg",
        },
        {
          id: 2,
          type: "image",
          title: "三屏幕显示器支架",
          name: "三屏幕显示器支架显示器桌面安装架夹桌子显示器支架显示器挂架",
          url: "https://cbu01.alicdn.com/img/ibank/O1CN01B6pK281oQM2CBIi2a_!!2214181785219-0-cib.jpg",
        },
        {
          id: 3,
          type: "image",
          title: "13-34显示器支架显示屏曲面屏支架",
          name: "13-34显示器支架显示屏曲面屏支架双臂气弹簧支架电脑支架",
          url: "https://cbu01.alicdn.com/img/ibank/O1CN01z4aDqb1oQM4GXrtog_!!2214181785219-0-cib.jpg",
        },
      ],
      /* tabs*/
      current: 0,
      fixedList: [
        { name: "显示器增高架" },
        { name: "显示器支架" },
        { name: "音响支架" },
        { name: "DVD支架" },
      ],
      /* 瀑布流*/
      loadStatus: "loadmore",
      list: [],
      componentKey: 0,
      data: [
        {
          title: "显示器增高架",
          userName: "电脑支架可升降笔记本台式底座增高架显示器增高架",
          mainImage:
            "https://cbu01.alicdn.com/img/ibank/O1CN01T5APES1oQM203aHRw_!!2214181785219-0-cib.310x310.jpg",
          userImage:
            "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
          storeType: 1, // 1 自营 2 第三方店铺
          newProduct: true, // 是否为新品
          tags: ["电脑支架"],
          viewUser: {
            latestUserAvatar: [
              {
                src: "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
              },
              {
                src: "https://resource.tuniaokj.com/images/blogger/avatar_2.jpeg",
              },
              {
                src: "https://resource.tuniaokj.com/images/blogger/avatar_3.jpeg",
              },
              {
                src: "https://resource.tuniaokj.com/images/blogger/avatar_4.jpeg",
              },
            ],
            viewUserCount: 338,
          },
          category: "显示器增高架",
        },
        {
          title: "跨境电商增高架台式电脑",
          userName: "跨境电商增高架台式电脑增高架笔记本电脑增高台显示器增高架",
          mainImage:
            "https://cbu01.alicdn.com/img/ibank/O1CN01JIcySf1oQM4gymUUO_!!2214181785219-0-cib.310x310.jpg",
          userImage:
            "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
          storeType: 1, // 1 自营 2 第三方店铺
          newProduct: true, // 是否为新品
          tags: ["台式电脑增高架", "电脑增高"],
          viewUser: {
            latestUserAvatar: [
              {
                src: "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
              },
              {
                src: "https://resource.tuniaokj.com/images/blogger/avatar_2.jpeg",
              },
              {
                src: "https://resource.tuniaokj.com/images/blogger/avatar_3.jpeg",
              },
              {
                src: "https://resource.tuniaokj.com/images/blogger/avatar_4.jpeg",
              },
            ],
            viewUserCount: 338,
          },
        },
        {
          title: "跨境电商增高架台式电脑",
          userName:
            "跨境电商增高架台式电脑增高架笔记本电脑增高台显示器增高架承重",
          mainImage:
            "https://cbu01.alicdn.com/img/ibank/O1CN01C1u0pL1oQM48JcbBb_!!2214181785219-0-cib.jpg",
          userImage:
            "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
          storeType: 1, // 1 自营 2 第三方店铺
          newProduct: true, // 是否为新品
          tags: ["台式电脑增高架", "电脑增高"],
          viewUser: {
            latestUserAvatar: [
              {
                src: "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
              },
              {
                src: "https://resource.tuniaokj.com/images/blogger/avatar_2.jpeg",
              },
              {
                src: "https://resource.tuniaokj.com/images/blogger/avatar_3.jpeg",
              },
              {
                src: "https://resource.tuniaokj.com/images/blogger/avatar_4.jpeg",
              },
            ],
            viewUserCount: 338,
          },
        },

        {
          title: "跨境电商增高架台式电脑",
          userName:
            "跨境电商增高架台式电脑增高架笔记本电脑增高台显示器增高架承重",
          mainImage:
            "https://cbu01.alicdn.com/img/ibank/O1CN01ZL4Q3Y1oQM29fQ3m7_!!2214181785219-0-cib.jpg",
          userImage:
            "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
          storeType: 1, // 1 自营 2 第三方店铺
          newProduct: true, // 是否为新品
          tags: ["台式电脑增高架", "电脑增高"],
          viewUser: {
            latestUserAvatar: [
              {
                src: "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
              },
              {
                src: "https://resource.tuniaokj.com/images/blogger/avatar_2.jpeg",
              },
              {
                src: "https://resource.tuniaokj.com/images/blogger/avatar_3.jpeg",
              },
              {
                src: "https://resource.tuniaokj.com/images/blogger/avatar_4.jpeg",
              },
            ],
            viewUserCount: 338,
          },
        },

        {
          title: "跨境电商增高架台式电脑",
          userName:
            "电脑增高架笔记本电脑增高台金属增高家用电脑增高架台式",
          mainImage:
            "https://cbu01.alicdn.com/img/ibank/O1CN01alLVRw1oQLueGQuSM_!!2214181785219-0-cib.jpg",
          userImage:
            "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
          storeType: 1, // 1 自营 2 第三方店铺
          newProduct: true, // 是否为新品
          tags: ["台式电脑增高架", "电脑增高"],
          viewUser: {
            latestUserAvatar: [
              {
                src: "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
              },
              {
                src: "https://resource.tuniaokj.com/images/blogger/avatar_2.jpeg",
              },
              {
                src: "https://resource.tuniaokj.com/images/blogger/avatar_3.jpeg",
              },
              {
                src: "https://resource.tuniaokj.com/images/blogger/avatar_4.jpeg",
              },
            ],
            viewUserCount: 338,
          },
        },


        
      ],
    };
  },
  /* 瀑布流*/
  created() {
    // this.getRandomData();

    this.list = this.data
  },
  onReachBottom() {},
  methods: {
    // cardSwiper
    cardSwiper(e) {
      this.cardCur = e.detail.current;
    },

    // 跳转
    tn(e) {
      uni.navigateTo({
        url: e,
      });
    },
    // tab选项卡切换
    tabChange(index) {
      this.current = index;
      console.log('Current tab index:', this.current);
      if (index == 1) {
        // 设置 this.list 为 index == 1 时的数据
        this.list = [
          {
            id: 1,
            title: "全动态显示器桌面支架夹具式双屏显示器支架",
            userName: "全动态显示器桌面支架夹具式双屏显示器支架夹桌支架显示器挂",
            mainImage:
              "https://cbu01.alicdn.com/img/ibank/O1CN01nY8AVu1oQM2EGLCxz_!!2214181785219-0-cib.310x310.jpg",
            userImage:
              "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
            storeType: 1, // 1 自营 2 第三方店铺
            newProduct: true, // 是否为新品
            tags: ["电脑支架"],
            viewUser: {
              latestUserAvatar: [
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_2.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_3.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_4.jpeg",
                },
              ],
              viewUserCount: 338,
            },
            category: "显示器增高架",
          },
          {
            id: 1,
            title: "单臂气弹簧支架电脑支架",
            userName: "显示器支架显示屏曲面屏支架单臂气弹簧支架电脑支架",
            mainImage:
              "https://cbu01.alicdn.com/img/ibank/O1CN01XTBJMv1oQM4g0uJgG_!!2214181785219-0-cib.jpg",
            userImage:
              "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
            storeType: 1, // 1 自营 2 第三方店铺
            newProduct: true, // 是否为新品
            tags: ["电脑支架"],
            viewUser: {
              latestUserAvatar: [
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_2.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_3.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_4.jpeg",
                },
              ],
              viewUserCount: 338,
            },
            category: "显示器增高架",
          },
          {
            id: 1,
            title: "跨境电商增高架台式电脑增高架笔记本电脑增高台显示器增高架承重",
            userName: "显示器支架显示屏曲面屏支架单臂气弹簧支架电脑支架",
            mainImage:
              " https://cbu01.alicdn.com/img/ibank/O1CN01ZL4Q3Y1oQM29fQ3m7_!!2214181785219-0-cib.jpg",
            userImage:
              "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
            storeType: 1, // 1 自营 2 第三方店铺
            newProduct: true, // 是否为新品
            tags: ["电脑支架"],
            viewUser: {
              latestUserAvatar: [
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_2.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_3.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_4.jpeg",
                },
              ],
              viewUserCount: 338,
            },
            category: "显示器增高架",
          },
          {
            id: 1,
            title: "现货笔记本支架桌面液晶显示器两用电脑升降可旋转双屏支架",
            userName: "显示器支架显示屏曲面屏支架单臂气弹簧支架电脑支架",
            mainImage:
              "https://cbu01.alicdn.com/img/ibank/O1CN017pxm2K1oQLsjmScly_!!2214181785219-0-cib.jpg",
            userImage:
              "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
            storeType: 1, // 1 自营 2 第三方店铺
            newProduct: true, // 是否为新品
            tags: ["电脑支架"],
            viewUser: {
              latestUserAvatar: [
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_2.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_3.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_4.jpeg",
                },
              ],
              viewUserCount: 338,
            },
            category: "显示器增高架",
          },
          {
            id: 1,
            title: "笔记本电脑托盘桌面支架笔记本支架显示器支架笔记本托支架",
            userName: "显示器支架显示屏曲面屏支架单臂气弹簧支架电脑支架",
            mainImage:
              "https://cbu01.alicdn.com/img/ibank/O1CN01ITfGNg1oQM2Cu0y1c_!!2214181785219-0-cib.jpg",
            userImage:
              "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
            storeType: 1, // 1 自营 2 第三方店铺
            newProduct: true, // 是否为新品
            tags: ["电脑支架"],
            viewUser: {
              latestUserAvatar: [
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_2.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_3.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_4.jpeg",
                },
              ],
              viewUserCount: 338,
            },
            category: "显示器增高架",
          },
        ];
        console.log('Updated list:', this.list);
      } else  if (index == 2) {
        // 设置 this.list 为 index == 1 时的数据
        this.list = [
          {
            id: 1,
            title: "音箱壁挂架音响支架音响用于大型环绕音响扬声器支架",
            userName: "全动态显示器桌面支架夹具式双屏显示器支架夹桌支架显示器挂",
            mainImage:
              "https://cbu01.alicdn.com/img/ibank/O1CN01T3FKyY1oQM2fvK5OV_!!2214181785219-0-cib.jpg",
            userImage:
              "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
            storeType: 1, // 1 自营 2 第三方店铺
            newProduct: true, // 是否为新品
            tags: ["音响支架"],
            viewUser: {
              latestUserAvatar: [
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_2.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_3.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_4.jpeg",
                },
              ],
              viewUserCount: 338,
            },
            category: "显示器增高架",
          },
        ];
        console.log('Updated list:', this.list);


        
      } 
      else  if (index == 4) {
        // 设置 this.list 为 index == 1 时的数据
        this.list = [
        

        {
            id: 1,
            title: "机顶盒挂架 / 机顶盒支架 /DVD支架/玻璃支架/双层玻璃支架",
            userName: "全动态显示器桌面支架夹具式双屏显示器支架夹桌支架显示器挂",
            mainImage:
              " https://cbu01.alicdn.com/img/ibank/O1CN01mxf4CS1oQM22RZqDe_!!2214181785219-0-cib.jpg",
            userImage:
              "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
            storeType: 1, // 1 自营 2 第三方店铺
            newProduct: true, // 是否为新品
            tags: ["机顶盒挂架"],
            viewUser: {
              latestUserAvatar: [
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_2.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_3.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_4.jpeg",
                },
              ],
              viewUserCount: 338,
            },
            category: "显示器增高架",
          },
          {
            id: 1,
            title: "机顶盒挂架 / 机顶盒支架 /DVD支架/玻璃支架/双层玻璃支架",
            userName: "全动态显示器桌面支架夹具式双屏显示器支架夹桌支架显示器挂",
            mainImage:
              "  https://cbu01.alicdn.com/img/ibank/O1CN01unJeDa1oQM1zLMr29_!!2214181785219-0-cib.jpg",
            userImage:
              "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
            storeType: 1, // 1 自营 2 第三方店铺
            newProduct: true, // 是否为新品
            tags: ["机顶盒挂架"],
            viewUser: {
              latestUserAvatar: [
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_1.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_2.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_3.jpeg",
                },
                {
                  src: "https://resource.tuniaokj.com/images/blogger/avatar_4.jpeg",
                },
              ],
              viewUserCount: 338,
            },
            category: "显示器增高架",
          },
        ];
        console.log('Updated list:', this.list);


      
      } else {


        
        // 处理其他 index 的情况
        this.list = this.data; // 或者根据需要设置其他数据
      }
    },
    /* 瀑布流*/
    // 获取随机数据
    getRandomData() {
      this.loadStatus = "loading";
      this.list = this.data.map(item => {
        let price = this.getPrice(item.price);
        return {
          ...item,
          id: this.$t.uuid(),
          priceInteger: price[0],
          priceDecimal: price[1]
        };
      });
      console.log(this.list, 'list');
      
      this.loadStatus = "loadmore";
    },
    // 瀑布流加载完毕事件
    handleWaterFallFinish() {
      this.loadStatus = "loadmore";
    },
  },
};
</script>

<style lang="scss" scoped>
.content_box{
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  .item_box {
    width: 49%;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    margin-top: 20px;
  }
  .item__image{
    width: 90%;
    height: 300rpx;
    border-radius: 10rpx;
    background-size: 100% 100%;
  }



  .item__store-type{
    height: 28rpx;
    font-size: 40rpx;
    position: relative;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: 4rpx;
    border-radius: 6rpx;
    white-space: nowrap;
    text-align: center;
    top: -2rpx;
    margin-right: 6rpx;

  }


  .item__tags{
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    align-items: center;
    justify-content: flex-end;


    .tag{
      margin: 10rpx;
      color: #7c8191;
      background-color: #f3f2f7;
      padding: 4rpx 14rpx 6rpx;
      border-radius: 10rpx;
      font-size: 20rpx;
      &:first-child{
        margin-left: 0 !important;
      }
    }
  }
  
}

.discovery {
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
    margin-left: 30rpx;
    margin-top: 5rpx;
    font-size: 40rpx;
    flex-basis: 5%;
    width: 100rpx;
  }
}
/* 自定义导航栏内容 end */

/* 轮播视觉差 start */
.card-swiper {
  height: 800rpx !important;
}

.card-swiper swiper-item {
  width: 750rpx !important;
  left: 0rpx;
  box-sizing: border-box;
  // padding: 0rpx 30rpx 90rpx 30rpx;
  overflow: initial;
}

.card-swiper swiper-item .swiper-item {
  width: 100%;
  display: block;
  height: 100%;
  transform: scale(1);
  transition: all 0.2s ease-in 0s;
  overflow: hidden;
}

.card-swiper swiper-item.cur .swiper-item {
  transform: none;
  transition: all 0.2s ease-in 0s;
}

.card-swiper swiper-item .swiper-item-text {
  // background-color: rgba(0, 0, 0, 0.7);
  background-image: linear-gradient(
    0deg,
    rgba(0, 0, 0, 0.7),
    rgba(0, 0, 0, 0.05)
  );
  margin-top: -260rpx;
  width: 100%;
  display: block;
  height: 50%;
  // border-radius: 10rpx;
  transform: translate(0rpx, 0rpx) scale(1);
  transition: all 0.6s ease 0s;
  overflow: hidden;
}

.card-swiper swiper-item.cur .swiper-item-text {
  // background-color: rgba(0, 0, 0, 0.7);
  background-image: linear-gradient(
    0deg,
    rgba(0, 0, 0, 0.7),
    rgba(0, 0, 0, 0.04)
  );
  margin-top: -260rpx;
  width: 100%;
  transform: translate(0rpx, 0rpx) scale(1);
  transition: all 0.6s ease 0s;
}

.card-swiper swiper-item .swiper-item-title {
  transform: translate(50rpx, 0rpx) scale(0.9);
  transition: all 0.6s ease 0s;
  overflow: hidden;
}

.card-swiper swiper-item.cur .swiper-item-title {
  transform: translate(0rpx, 0rpx) scale(1);
  transition: all 0.6s ease 0s;
}

.image-banner {
  display: flex;
  align-items: center;
  justify-content: center;
}
.image-banner image {
  width: 100%;
  height: 100%;
}

/* 轮播指示点 start*/
.indication {
  z-index: 9999;
  width: 100%;
  height: 36rpx;
  position: absolute;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}

.spot {
  background-color: #ffffff;
  opacity: 0.6;
  width: 10rpx;
  height: 10rpx;
  border-radius: 20rpx;
  top: -60rpx;
  margin: 0 8rpx !important;
  position: relative;
}

.spot.active {
  opacity: 1;
  width: 30rpx;
  background-color: #ffffff;
}

/* 用户头像 start */
.logo-image {
  width: 40rpx;
  height: 40rpx;
  position: relative;
}

.logo-pic {
  background-size: cover;
  background-repeat: no-repeat;
  // background-attachment:fixed;
  background-position: top;
  border: 1rpx solid rgba(255, 255, 255, 0.05);
  // box-shadow: 0rpx 0rpx 80rpx 0rpx rgba(0, 0, 0, 0.15);
  border-radius: 50%;
  overflow: hidden;
  // background-color: #FFFFFF;
}

/* 瀑布流*/
.product__item {
  background-color: #ffffff;
  overflow: hidden;
  margin: 0 10rpx;
  margin-bottom: 40rpx;
  // box-shadow: 0rpx 0rpx 30rpx 0rpx rgba(0, 0, 0, 0.07);

  .item {
    /* 图片 start */
    &__image {
      width: 100%;
      height: auto;
      background-color: #ffffff;
      border: 1rpx solid #f8f7f8;
      border-radius: 10rpx;
      overflow: hidden;
    }
    /* 图片 end */

    /* 内容 start */
    &__data {
      padding: 14rpx 0rpx;
    }

    /* 标题 start */
    &__title-container {
      text-align: justify;
      line-height: 38rpx;
      vertical-align: middle;
    }
    &__store-type {
      height: 28rpx;
      font-size: 20rpx;
      position: relative;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 4rpx;
      border-radius: 6rpx;
      white-space: nowrap;
      text-align: center;
      top: -2rpx;
      margin-right: 6rpx;
    }
    &__title {
      font-size: 30rpx;
    }
    /* 标题 end */

    /* 标签 start */
    &__tags-container {
      display: flex;
      flex-direction: row;
      flex-wrap: nowrap;
      align-items: center;
      justify-content: flex-start;
    }
    &__tag {
      margin: 10rpx;
      color: #7c8191;
      background-color: #f3f2f7;
      padding: 4rpx 14rpx 6rpx;
      border-radius: 10rpx;
      font-size: 20rpx;

      &:first-child {
        margin-left: 0rpx !important;
      }
    }
    /* 标签 end */

    /* 价格 start */
    &__price-container {
      font-size: 24rpx;
      color: #e83a30;
      font-weight: bold;
    }
    &__price {
      &--unit {
      }
      &--integer {
        font-size: 38rpx;
      }
      &--decimal {
      }
    }
    /* 价格 end */
    /* 内容 end */
  }
}
</style>
