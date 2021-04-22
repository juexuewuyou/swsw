<template>
  <div>
    <!-- 顶部 -->
<mt-tab-container v-model="active">
  <mt-tab-container-item id="nv">
    <mt-cell title="tab-container 1">
      111111111
    </mt-cell>
  </mt-tab-container-item>
  <mt-tab-container-item id="nan">
    <mt-cell title="tab-container 2">
      2222222
    </mt-cell>
  </mt-tab-container-item>
  <mt-tab-container-item id="tab-container3">
    <mt-cell title="tab-container 3">
      3333333
    </mt-cell>
  </mt-tab-container-item>
</mt-tab-container>

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
        <img v-if="selected=='sc'" slot="icon" src="../assets/icon/sc_1.png" />
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
        <img v-if="selected=='wd'" slot="icon" src="../assets/icon/wd_1.png" />
        <img v-else slot="icon" src="../assets/icon/wd_0.png" />
        我的
      </mt-tab-item>
    </mt-tabbar>
  </div>
</template>
<script>
export default {
  data() {
    return {
      selected: "sj",
      active:"nv"
    };
  },
  watch:{
    selected(val){
      if(val=='sj'){
        this.$router.push('/shouye')
      }else if(val=='sc'){
        this.$router.push('/shucheng')
      }else if(val=='fl'){
        this.$router.push('/fenlei')
      }else if(val=='wd'){
        this.$router.push('/wode')
      }
    }
  }
};
</script>