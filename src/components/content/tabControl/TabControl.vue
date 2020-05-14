<template>
  <div class="tab-control">
    <div
      v-for="(item,key) in titles"
      :key="key"
      class="tab-control-item"
      :class="{active : key === currentIndex}"
      @click="itemClick(key)"
    >
      <span>{{item}}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "TabControl",
  props: {
    titles: {
      type: Array,
      default() {
        return [];
      }
    }
  },
  data() {
    return {
      currentIndex: 0
    };
  },
  methods:{
    itemClick(index){
      this.currentIndex=index
    }
  }
};
</script>
<style lang='scss' scoped>
.tab-control {
  display: flex;
  text-align: center;
  font-size: 15px;
  height: 40px;
  line-height: 40px;
  background-color: #fff;
}
.tab-control-item {
  flex: 1;
}
.active {
  color: #fb7299;
}
.active span {
  border-bottom: 3px solid #fb7290;
}
</style>
