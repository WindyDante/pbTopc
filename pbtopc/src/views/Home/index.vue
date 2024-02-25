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
      <el-main>
        <el-card
          shadow="hover"
          style="width: 1000px; height: 100px; margin: 0 auto"
        >
          <div>科技助力，农业发展更有活力</div>
          <ul>
            <li>
              <ul style="display: flex">
                <li style="flex: 12">“火焰蓝”开展应急演练 锤炼救援真本领</li>
                <li style="flex: 12">
                  检察公益诉讼多元破解老年人权益保障难题凝聚合力托起“夕阳红
                </li>
              </ul>
            </li>
            <li>
              <ul style="display: flex">
                <li style="flex: 12">
                  媒体医声｜科普赋能，普陀区精神卫生中心做孩子的心灵“守门人
                </li>
                <li style="flex: 12">
                  交通部门健全春运应急预案确保旅客安全出行
                </li>
              </ul>
            </li>
            <li>
              <ul style="display: flex">
                <li style="flex: 12">
                  民生直通车丨功能更多元，社保卡将实现全国“一卡通”
                </li>
                <li style="flex: 12">深圳体彩去年筹集公益金21.10亿</li>
              </ul>
            </li>
          </ul>
        </el-card>
        <el-carousel height="290px" style="width: 400px">
          <el-carousel-item v-for="item in picList" :key="item.id">
            <img :src="item.imgSrc" alt="" style="width: 100%" />
          </el-carousel-item>
        </el-carousel>
        <!-- 详情页 -->
        <div
          style="
            width: 1100px;
            height: auto;
            margin: 0 auto;
            display: flex;
            flex-wrap: wrap;
          "
        >
          <ul
            style="
              border: 1px solid #ccc;
              width: 350px;
              height: 400px;
              margin: 5px 0 0 5px;
            "
            v-for="item in picList2"
            :key="item.id"
          >
            <li style="border-bottom: 1px solid #ccc">锐视</li>
            <img
              :src="item.imgSrc"
              alt=""
              style="width: 100%; height: 250px"
            />
            <li>边游边学</li>
            <li>"应急救护 救在身边"</li>
            <li>《华夏志愿者》 编辑部征稿启事</li>
            <li>2022年度全国爱国卫生运动大会健康</li>
            <li>98岁宝藏老人火了：在图书馆当</li>
          </ul>
        </div>
      </el-main>
      <el-footer> </el-footer>
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
      picList: [
        { id: 1, imgSrc: require("@/assets/images/pic1.png") },
        { id: 2, imgSrc: require("@/assets/images/pic2.png") },
        { id: 3, imgSrc: require("@/assets/images/pic3.jpg") },
        { id: 4, imgSrc: require("@/assets/images/pic4.png") },
        { id: 5, imgSrc: require("@/assets/images/pic5.png") },
      ],
      picList2: [
        { id: 1, imgSrc: require("@/assets/images/pic6.jpg") },
        { id: 2, imgSrc: require("@/assets/images/pic7.jpg") },
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
li {
  list-style-type: none;
}
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