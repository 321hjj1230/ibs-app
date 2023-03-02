<template>
  <div><h2 style="font-size: 0.4rem;margin-inline: 0.2rem;margin-block: 12px;">IBS健康管理</h2></div>
  <div class="home">
    <top-nav style="position:fixed;bottom:0px"></top-nav>
    <van-swipe :autoplay="3000" style="margin: 5px;">
  <van-swipe-item v-for="(image, index) in images" :key="index" style="background-color: aqua;height: 3rem;">
    <!-- <img v-lazy="image" /> -->
    {{ image }}
  </van-swipe-item>
</van-swipe>

<divide></divide>
<icon-list></icon-list>

    <div class="fenjiexian"><span class=midText></span></div>

  </div>
</template>

<script>
// @ is an alias to /src
import topNav from '@/components/line/topNav.vue'
import iconList from '@/components/line/iconList.vue'
import Divide from '@/components/line/divide.vue'

export default {
  name: 'HomeView',
  components: {
    topNav,
    iconList,
    Divide,
  },
  data() {
    return {
      images: [
        '1',
        'https://img.yzcdn.cn/2.jpg'
      ]
    }}
}
</script>

<style lang="less" scoped>
  .fenjiexian{
    position: relative;
    margin: 0 aoto;
    width: 100%;
    background-color: #d4d4d4;
    text-align: center;
    color: rgba(101,101,101,1);
    margin-bottom:0.2rem;
  }
  .midText{
    height: 0.15rem;
    position: absolute;
    background-color: #ffffff;
    padding: 0 15px;
    transform: translateX(-50%) translateY(-50%);
  }


</style>