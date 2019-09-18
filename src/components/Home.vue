<template>
  <div class="wrap">
    <div class="search">
      <el-input class="input" v-model="input" placeholder="请输入搜索内容"></el-input>
      <i class="el-icon-search"></i>
    </div>
    <div class="banner">
      <swiper :options="swiperOption" ref="mySwiper" class="swiper">
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
      <h3>视频总览</h3>
    </div>
    <div class="video-wrap" >

      <div class="item-video"  v-for="(item,i) in videoList">
        <a :href="item.link">
          <img class="cover" :src="item.image" alt />
        </a>
        <span class="title">简介：{{item.title}}</span>
        <span class="auth">播放量：100</span>
      </div>

    </div>
  </div>
</template>

<script>
// require styles
const axios = require("axios");
import "swiper/dist/css/swiper.css";
import { swiper, swiperSlide } from "vue-awesome-swiper";
export default {
  components: {
    swiper,
    swiperSlide
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
        spaceBetween: 10
      },
      input: "",
      videoList:[]
    };
  },
  mounted() {
    this.login();
    var t = localStorage.getItem("token");
    console.log("toke111n", t);
    if (t) {
      var formData = new FormData();
      formData.append("token", t);
      axios
        .post("/api/index/Get/videoList", formData)
        .then(res => {
          if(res.data.code==1){
            console.log('视频列表',res.data.data.list);
           this.videoList  =  res.data.data.list
          }
          
        })
        .catch(function(error) {
          console.log(error);
        });
    }
  },
  methods: {
    login() {
      var formData = new FormData();
      formData.append("reg_time", "1565705006");
      formData.append("sign", "0C53773259CA766DA8711307009F7E48");
      formData.append("deviceID", "ffffffff-878c-8d59-0000-000038b603fd");
      axios
        .post("/api/index/register/app_reg", formData, {
          headers: { "Content-Type": "application/x-www-form-urlencoded" }
        })
        .then(res => {
          console.log("token", res.data.token);
          if (res.data.token) {
            localStorage.setItem("token", res.data.token);
          } else {
            console.log("获取token失败");
          }
        })
        .catch(function(error) {
          console.log(error);
        });
    }
  }
};
</script>

<style lang="less" scoped>
.wrap {
  width: 100%;
  height: 100%;
  .search {
    position: relative;
    i {
      position: absolute;
      right: 2rem;
      top: 1.8rem;
      color: #dcdfe6;
    }
  }
  .input {
    width: 22rem;
    margin: 1rem 0.64rem;
  }
  .banner {
    margin: 0 0.64rem;
  }
  .block-title {
    margin: 0 0.64rem;
    margin-top: 0.72rem;
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
    margin: 0 0.64rem;
    justify-content: space-between;
    .item-video {
      flex-direction: column;
      display: flex;
      margin-top: 0.75rem;
      .cover {
        width: 10.6375rem;
        height: 25.07vw;
        border-radius: 0.05rem;
      }
      .title {
        font-size: 0.56rem;
        color: #000028;
        margin-top: 0.375rem;
      }
      .auth {
        font-size: 0.48rem;
        color: #a2a2b6;
        margin-top: 0.25rem;
      }
    }
  }
}
</style>
