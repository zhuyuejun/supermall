import { getHomeMultidata, getHomeMultidata111 } from "../../network/home";

<template>
  <div id="home">
    <Navbar class="home-nav">
      <div slot="center">购物街</div>
    </Navbar>
    <HomeSwiper :banners="banners" />
    <RecommendView :recommends="recommends" />
    <FeatureView />
    <TabControl class="tab-control" :titles="['流行','新款','精选']"/>

    <ul>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
      <li>11111111111111</li>
    </ul>
  </div>
</template>

<script>

import HomeSwiper from "./childComps/HomeSwiper";
import RecommendView from "./childComps/RecommendView";
import FeatureView from "./childComps/FeatureView";

import Navbar from "components/common/navbar/NavBar";
import TabControl from "components/content/tabControl/TabControl";
// 大括号导入是因为 export 导出不是 default
import { getHomeMultidata } from "network/home";



export default {
  name: "Home",
  components: {
    Navbar,
    HomeSwiper,
    RecommendView,
    FeatureView,
    TabControl
  },
  data() {
    return {
      banners: [],
      recommends: []
    };
  },
  created() {
    getHomeMultidata().then(res => {
      console.log(res);
      this.banners = res.data.banner.list;
      this.recommends = res.data.recommend.list;
    });
  }
};
</script>

<style lang='scss' scoped>
#home{
  padding-top: 44px;
}
.home-nav {
  background-color: #fb7299;
  color: #fff;

  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  z-index: 9;
}
.tab-control{
  position: sticky;
  top: 44px;
}
</style>
