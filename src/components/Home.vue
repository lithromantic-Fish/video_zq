<template>
  <div class="wrap">
    <div class="search">
      <el-input class="input"  v-model="input" placeholder="请输入搜索内容">
      </el-input>
      <i class="el-icon-search"></i>
    </div>
    <div class="banner">
      <swiper :options="swiperOption" ref="mySwiper"  class="swiper">
        <!-- slides -->
        <swiper-slide>
          <img src="../assets/test.png" alt />
        </swiper-slide>
        <swiper-slide>
          <img src="../assets/test.png" alt />
        </swiper-slide>
        <swiper-slide>
          <img src="../assets/test.png" alt />
        </swiper-slide>
        <swiper-slide>
          <img src="../assets/test.png" alt />
        </swiper-slide>
        <swiper-slide>
          <img src="../assets/test.png" alt />
        </swiper-slide>
        <swiper-slide>
          <img src="../assets/test.png" alt />
        </swiper-slide>
      </swiper>
    </div>
    <div class="block-title">
        <h3>猜你喜欢</h3>
    </div>
    <div class="video-wrap">
      <div class="item-video">
        <img class="cover" src="../assets/test.png" alt />
        <span class="title">简介：这是条有意思的视频</span>
        <span class="auth">播放量：100</span>
      </div>
      <div class="item-video">
        <img class="cover" src="../assets/test.png" alt />
        <span class="title">简介：这是条有意思的视频</span>
        <span class="auth">播放量：100</span>
      </div>
      <div class="item-video">
        <img class="cover" src="../assets/test.png" alt />
        <span class="title">简介：这是条有意思的视频</span>
        <span class="auth">播放量：100</span>
      </div>
      <div class="item-video">
        <img class="cover" src="../assets/test.png" alt />
        <span class="title">简介：这是条有意思的视频</span>
        <span class="auth">播放量：100</span>
      </div>
    </div>
    <div class="block-title">
        <h3>电影</h3>
    </div>
    <div class="video-wrap">
      <div class="item-video">
        <img class="cover" src="../assets/test.png" alt />
        <span class="title">简介：这是条有意思的视频</span>
        <span class="auth">播放量：100</span>
      </div>
      <div class="item-video">
        <img class="cover" src="../assets/test.png" alt />
        <span class="title">简介：这是条有意思的视频</span>
        <span class="auth">播放量：100</span>
      </div>
      <div class="item-video">
        <img class="cover" src="../assets/test.png" alt />
        <span class="title">简介：这是条有意思的视频</span>
        <span class="auth">播放量：100</span>
      </div>
      <div class="item-video">
        <img class="cover" src="../assets/test.png" alt />
        <span class="title">简介：这是条有意思的视频</span>
        <span class="auth">播放量：100</span>
      </div>
    </div>
    <div class="block-title">
        <h3>综艺</h3>
    </div>
    <div class="video-wrap">
      <div class="item-video">
        <img class="cover" src="../assets/test.png" alt />
        <span class="title">简介：这是条有意思的视频</span>
        <span class="auth">播放量：100</span>
      </div>
      <div class="item-video">
        <img class="cover" src="../assets/test.png" alt />
        <span class="title">简介：这是条有意思的视频</span>
        <span class="auth">播放量：100</span>
      </div>
      <div class="item-video">
        <img class="cover" src="../assets/test.png" alt />
        <span class="title">简介：这是条有意思的视频</span>
        <span class="auth">播放量：100</span>
      </div>
      <div class="item-video">
        <img class="cover" src="../assets/test.png" alt />
        <span class="title">简介：这是条有意思的视频</span>
        <span class="auth">播放量：100</span>
      </div>
    </div>
    <div class="block-title">
        <h3>动漫</h3>
    </div>
    <div class="video-wrap">
      <div class="item-video">
        <img class="cover" src="../assets/test.png" alt />
        <span class="title">简介：这是条有意思的视频</span>
        <span class="auth">播放量：100</span>
      </div>
      <div class="item-video">
        <img class="cover" src="../assets/test.png" alt />
        <span class="title">简介：这是条有意思的视频</span>
        <span class="auth">播放量：100</span>
      </div>
      <div class="item-video">
        <img class="cover" src="../assets/test.png" alt />
        <span class="title">简介：这是条有意思的视频</span>
        <span class="auth">播放量：100</span>
      </div>
      <div class="item-video">
        <img class="cover" src="../assets/test.png" alt />
        <span class="title">简介：这是条有意思的视频</span>
        <span class="auth">播放量：100</span>
      </div>
    </div>
  </div>
</template>

<script>
// require styles
import "swiper/dist/css/swiper.css";
import { swiper, swiperSlide } from "vue-awesome-swiper";
export default {
  components: {
    swiper,
    swiperSlide,
  },
  name: "HelloWorld",
  data() {
    return {
      swiperOption: {
        loop: true,
        autoplay: {
          delay: 2500,
          disableOnInteraction: false
        },
        freeMode: false,
        spaceBetween: 10,

      },
      input:''
    };
  },
  mounted() {
  }
};
</script>

<style lang="less" scoped>
.wrap {
  width: 100%;
  height: 100%;
  .search{
    position: relative;
    i{
     position: absolute;
      right: 2rem;
      top: 1.8rem;
      color: #DCDFE6
    }
  }
  .input{
    width: 22rem;
    margin: 1rem .64rem

  }
  .banner{
    margin: 0 .64rem;

  }
  .block-title{
    margin: 0 .64rem;
        margin-top: .72rem;
  }
  .swiper {
    .swiper-slide {
      img {
        width: 100%;
        height: 51vw;
      }
    }
  }

  .video-wrap {
    display: flex;
    flex-wrap: wrap;
    width: 22rem;
    margin: 0 .64rem;
    justify-content: space-between;
    .item-video {
      flex-direction: column;
      display: flex;
      margin-top: .75rem;
      .cover {
        width: 10.6375rem;
        height: 25.07vw;
        border-radius: .05rem
      }
      .title {
        font-size: .56rem;
        color: #000028;
        margin-top: .375rem
      }
      .auth{
        font-size: .48rem;
        color: #a2a2b6;
        margin-top: .25rem
      }

    }
  }
}
</style>
