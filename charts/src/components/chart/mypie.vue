<template>
  <div>
    <p class="title">入项数据</p>
    <div class="chart">
      <div class="pie"></div>
      <div class="pie1"></div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {};
  },
  mounted() {
    this.drawLine();
    this.drawLine1();
  },
  methods: {
    drawLine() {
      // 基于准备好的dom，初始化echarts实例
      let pie = this.$echarts.init(document.querySelector(".pie"));
      // 绘制图表
      pie.setOption({
        title: {
          text: "区域比例",
          subtext: "城市分布",
          left: "center",
        },
        tooltip: {
          trigger: "item",
          formatter: "{a} <br/>{b} : {c} ({d}%)",
        },
        legend: {
          orient: "vertical",
          left: "left",
          data: [
            "北京",
            "上海",
            "南京",
            "杭州",
            "苏州",
            "青岛",
            "烟台",
            "武汉",
            "郑州",
            "其他",
          ],
        },
        series: [
          {
            name: "访问来源",
            type: "pie",
            radius: "55%",
            center: ["60%", "60%"],
            data: [
              { value: 0, name: "北京" },
              { value: 100, name: "上海" },
              { value: 430, name: "南京" },
              { value: 135, name: "杭州" },
              { value: 208, name: "苏州" },
              { value: 585, name: "青岛" },
              { value: 70, name: "烟台" },
              { value: 74, name: "武汉" },
              { value: 185, name: "郑州" },
              { value: 380, name: "其他" },
            ],
            emphasis: {
              itemStyle: {
                shadowBlur: 10,
                shadowOffsetX: 0,
                shadowColor: "rgba(0, 0, 0, 0.5)",
              },
            },
          },
        ],
      });
    },
    drawLine1() {
      // 基于准备好的dom，初始化echarts实例
      let pie1 = this.$echarts.init(document.querySelector(".pie1"));
      // 绘制图表
      pie1.setOption({
        title: {
          text: "招聘来源",
          subtext: "来源分布",
          left: "center",
        },
        tooltip: {
          trigger: "item",
          formatter: "{a} <br/>{b} : {c} ({d}%)",
        },
        legend: {
          orient: "vertical",
          left: "left",
          data: ["机构", "BOSS", "智联", "社招", "其他(推荐等)"],
        },
        series: [
          {
            name: "访问来源",
            type: "pie",
            radius: "55%",
            center: ["60%", "60%"],
            data: [
              { value: 30, name: "机构" },
              { value: 24, name: "BOSS" },
              { value: 20, name: "智联" },
              { value: 12, name: "社招" },
              { value: 25, name: "其他(推荐等)" },
            ],
            emphasis: {
              itemStyle: {
                shadowBlur: 10,
                shadowOffsetX: 0,
                shadowColor: "rgba(0, 0, 0, 0.5)",
              },
            },
          },
        ],
      });
    },
  },
};
</script>
<style >
.chart {
  display: flex;
  justify-content: space-between;
}
.pie {
  width: 50%;
  height: 240px;
}
.pie1 {
  width: 50%;
  height: 240px;
}
.title {
  font-weight: 300;
  font-size: 14px;
  margin: 0px 0px 15px 0px;
}
</style>

