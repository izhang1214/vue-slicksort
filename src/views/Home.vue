<template>
  <div class="home">
    <HelloWorld msg="欢迎" />
    <div class="slicksort-wrap">
      <!-- 拖拽 -->
      <SlickList
        class="wrap-box"
        :lockToContainerEdges="true"
        axis="xy"
        lockAxis="y"
        v-model="goodsList"
        @input="getChangeLists"
      >
        <SlickItem
          class="item"
          v-for="(item, index) in goodsList"
          :index="index"
          :key="index"
        >{{ item }}</SlickItem>
      </SlickList>
    </div>
    <div>
      <img src="@/assets/zucan.jpg" alt />
      <img src="@/assets/event.jpg" alt />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import { SlickList, SlickItem } from "vue-slicksort";
export default {
  name: "Home",
  components: {
    HelloWorld,
    SlickList,
    SlickItem
  },
  data() {
    return {
      goodsList: [
        "商品",
        "手机",
        "衣服",
        "鞋帽",
        "箱包",
        "电脑",
        "零食",
        "化妆品"
      ]
    };
  },
  methods: {
    getChangeLists(event) {
      console.log(event);
    }
  }
};
</script>
<style>
.home {
  margin: auto;
}
.slicksort-wrap {
  width: 150px;
}
.wrap-box {
  width: 150px;
  display: flex;
  flex-wrap: wrap;
}
.slicksort-wrap .item {
  width: 50px;
  height: 50px;
  box-shadow: 0 0 0 1px rebeccapurple;
  box-sizing: border-box;
  line-height: 50px;
  text-align: center;
}
</style>
