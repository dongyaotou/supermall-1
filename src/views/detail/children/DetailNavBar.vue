<template>
  <div>
    <nav-bar>
      <div slot="left" class="back" @click="backClick">
        <img src="~assets/img/common/back.svg" alt="">
      </div>
      <div slot="center" class="title">
        <div
          v-for="(item,index) in titles"
          :key="index"
          :class="{active:index===currentIndex}"
          class="title-item"
          @click="titleClick(index)"
        >{{item}}</div>
      </div>
    </nav-bar>
  </div>
</template>

<script>
import NavBar from "components/common/navbar/NavBar";
export default {
  name: "DetailNavBar",
  data() {
    return {
      titles: ["商品", "参数", "评论", "推荐"],
      currentIndex: 0
    };
  },
  components: {
    NavBar
  },
  created() {},
  mounted() {},
  methods: {
    // 标题点击事件
    titleClick(index) {
      this.currentIndex = index;
    },
    backClick(){
      this.$router.go(-1);
    }
  }
};
</script>
<style lang='scss' scoped>
.title {
  display: flex;
}
.title-item {
  flex: 1;
}
.active {
  color: var(--color-high-text);
}
.back img{
  margin-top: 10px;
  margin-left: 15px;
}
</style>
