<template>
  <div>
    <el-container>
      <el-header style="height: 100%">
        <!-- 日期信息 -->
        <div class="HeaderForDay">{{ currentYMD }}</div>
        <!-- 分割线 -->
        <el-divider></el-divider>
        <!-- logo及商品购买区域,可被点击 -->
        <div class="LogoAndPay">
          <div>
            <img src="@/assets/tlzy.png" alt="" />
          </div>
        </div>
      </el-header>
      <el-main>Main</el-main>
      <el-footer>Footer</el-footer>
    </el-container>
  </div>
</template>

<script>
export default {
  name: "PbtopcHome",

  data() {
    return {};
  },

  mounted() {},
  computed: {
    // 当前的年月日及星期信息
    currentYMD() {
      let year = new Date().getFullYear();
      let month = new Date().getMonth() + 1;
      let day = new Date().getDate();
      let Sunday = new Date().getDay();
      switch (Sunday) {
        case 0:
          Sunday = "日";
          break;
        case 1:
          Sunday = "一";
          break;
        case 2:
          Sunday = "二";
          break;
        case 3:
          Sunday = "三";
          break;
        case 4:
          Sunday = "四";
          break;
        case 5:
          Sunday = "五";
          break;
        case 6:
          Sunday = "六";
          break;
      }
      return year + "年" + month + "月" + day + "日" + "星期" + Sunday;
    },
  },

  methods: {},
};
</script>

<style  scoped>
.LogoAndPay {
  display: flex;
  padding: 5px 20px;
  align-items: center;
}
.HeaderForDay {
  display: flex;
  align-items: center;
  font-size: 16px;
  padding: 5px 50px;
}
.el-divider--horizontal {
  margin: 10px 0;
}
</style>