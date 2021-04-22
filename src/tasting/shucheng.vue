<template>
  <div class="shucheng">
    <mt-header title="书城"></mt-header>
    <!-- 轮播图 -->
    <!-- testing/Swipe.vue -->
    <mt-swipe
      class="swipe"
      :style="{ height: h }"
      :auto="2000"
      :speed="300"
      :show-indicators="true"
      :continuous="true"
    >
      <mt-swipe-item>
        <img
          src="../assets/banner/banner5.webp"
          style="width: 100%"
          class="s_img"
          alt=""
        />
      </mt-swipe-item>
      <mt-swipe-item>
        <img
          src="../assets/banner/banner6.webp"
          style="width: 100%"
          class="s_img"
          alt=""
        />
      </mt-swipe-item>
      <mt-swipe-item>
        <img
          src="../assets/banner/banner7.webp"
          style="width: 100%"
          class="s_img"
          alt=""
        />
      </mt-swipe-item>
      <mt-swipe-item>
        <img src="../assets/banner/banner8.webp" style="width: 100%" alt="" />
      </mt-swipe-item>
    </mt-swipe>

    <!-- 二楼 -->
    <div id="er">
      <div class="erpdd">
        <div class="er_container">
          <div class="left">
            <div class="myleft">
              <!-- 内容区域 -->
              <div>
                <span>分类</span>
                <p>爽文·升级</p>
              </div>
            </div>
          </div>
          <div class="right">
            <div class="myright">
              <!-- 内容区域 -->
            </div>
          </div>
          <div class="bottom">
            <div class="mybottom">
              <!--内容区域 -->
            </div>
          </div>
          <div class="bottom">
            <div class="mybottom">
              <!--内容区域 -->
            </div>
          </div>
          <div class="bottom">
            <div class="mybottom">
              <!--内容区域 -->
            </div>
          </div>
          <!-- 二楼结束 -->
        </div>
      </div>
    </div>

    <!-- 三楼 -->
    <div class="san">
      <div class="f_ph">
        <div class="ph">
          <span>排行榜 · 4月21日</span>
          <span>完整榜单</span>
        </div>
      </div>
    </div>

    <!--路由嵌套  ╭榜单╮  -->

    <div class="bd"></div>

    <!-- 底部导航 -->
    <mt-tabbar v-model="selected" fixed>
      <mt-tab-item id="sj">
        <img
          v-if="selected == 'sj'"
          slot="icon"
          src="../assets/icon/sj_1.png"
        />
        <img v-else slot="icon" src="../assets/icon/sj_0.png" />
        书架
      </mt-tab-item>
      <mt-tab-item id="sc">
        <img
          v-if="selected == 'sc'"
          slot="icon"
          src="../assets/icon/sc_1.png"
        />
        <img v-else slot="icon" src="../assets/icon/sc_0.png" />
        书城
      </mt-tab-item>
      <mt-tab-item id="fl">
        <img
          v-if="selected == 'fl'"
          slot="icon"
          src="../assets/icon/fl_1.png"
        />
        <img v-else slot="icon" src="../assets/icon/fl_0.png" />
        分类
      </mt-tab-item>
      <mt-tab-item id="wd">
        <img
          v-if="selected == 'wd'"
          slot="icon"
          src="../assets/icon/wd_1.png"
        />
        <img v-else slot="icon" src="../assets/icon/wd_0.png" />
        我的
      </mt-tab-item>
    </mt-tabbar>
  </div>
</template>
<style>
.shucheng #er {
  width: 100%;
  height: 180px;
}
.shucheng #er .erpdd {
  padding: 10px;
}
.shucheng #er .er_container {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}
.shucheng #er .left {
  width: 50%;
  height: 100px;
  /* padding:2px; */
  /* display: flex; */
}
.shucheng #er .left .myleft {
  width: 98%;
  height: 98%;
  background: lightgoldenrodyellow;
  border-radius: 6px;
}
.shucheng #er .right {
  width: 50%;
  height: 100px;
}
.shucheng #er .right .myright {
  width: 98%;
  height: 98%;
  background: lightgray;
  border-radius: 6px;
}

.shucheng #er .er_container .bottom {
  width: 33.333333%;
  height: 80px;
}
.shucheng #er .er_container .bottom .mybottom {
  width: 96%;
  height: 96%;
  background: lightcyan;
  border-radius: 6px;
}
.shucheng .san .ph {
  display: flex;
  justify-content: space-between;
}
.shucheng .san .f_ph {
  padding: 16px;
  font-family: "simhei";
}
</style>
<script>
export default {
  data() {
    return {
      selected: "sc",
      active: "nv",
      h: "100px",
    };
  },
  watch: {
    selected(val) {
      if (val == "sj") {
        this.$router.push("/shouye");
      } else if (val == "sc") {
        this.$router.push("/shucheng");
      } else if (val == "fl") {
        this.$router.push("/fenlei");
      } else if (val == "wd") {
        this.$router.push("/wode");
      }
    },
  },
  mounted() {
    // 初始化适配轮播图的高度
    let picwidth = 1242;
    let picheight = 698;
    // 屏幕宽
    let screenwidth = window.screen.width;
    let height = Math.floor((picheight * screenwidth) / picwidth) + "px";
    // 把计算得到的height，赋值给data中的变量，动态更新轮播图
    this.h = height;
  },
};
</script>