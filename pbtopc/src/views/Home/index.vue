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
          <div class="RightMenu">
            <!-- forone -->
            <div class="forOneMenu">
              <img
                src="http://www.chinagongyi.com.cn/statics/images/sinaweibo.png"
                alt=""
              />
              <div>微博</div>
            </div>
            <!-- forone -->
            <div class="forOneMenu">
              <img
                src="http://www.chinagongyi.com.cn/statics/images/weixin.png"
                alt=""
              />
              <div>微信公众号</div>
            </div>
            <!-- forone -->
            <div class="forOneMenu">
              <img
                src="https://pic.mksucai.com/00/19/41/c7722947b97ac0ac.webp"
              />
              <div>抖音</div>
            </div>
          </div>
        </div>
        <div class="Nav">
          <div class="NavForOne" v-for="(i, index) in list" :key="index">
            <a>{{ i }}</a>
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
    return {
      list: [
        "工艺品",
        "纤维制品",
        "竹炭制品",
        "竹集成材",
        "日用品",
        "艺术作品",
        "旅游纪念品",
        "家具用品",
        "办公用品",
        "环保产品",
      ],
    };
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
.NavForOne {
  line-height: 60px;
  font-size: 16px;
  font-weight: 800;
  color: white;
}
.Nav {
  display: flex;
  justify-content: space-around;
  width: 100%;
  height: 60px;
  margin: 40px 0;
  background: #50bdff;
}
* {
  margin: 0;
  padding: 0;
}

.forOneMenu {
  display: flex;
  width: 30px;
  height: 30px;
  margin: 0 30px;
  flex-direction: column;
}
.RightMenu {
  display: flex;
  justify-content: space-around;
}
.LogoAndPay {
  display: flex;
  justify-content: space-around;
  padding: 5px 0px;
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