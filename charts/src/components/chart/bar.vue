<template>
  <div>
    <p class="title">入项数据</p>
    <div class="myChart"></div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      barmonth: ["三月", "四月", "五月", "六月", "七月", "八月", "九月"],
      barnum: [0.15, 0.15, 0.15, 3, 4, 5, 5],
    };
  },
  mounted() {
    this.drawLine();
  },
  methods: {
    drawLine() {
      // 基于准备好的dom，初始化echarts实例
      let myChart = this.$echarts.init(document.querySelector(".myChart"));
      // 绘制图表
      myChart.setOption({
        title: { text: "入项人数/月" },
        tooltip: { trigger: "item" },
        lineStyle: "#4ad2ff",
        grid: {
          left: "5%",
          right: "5%",
          bottom: "3%",
          containLabel: true,
        },
        xAxis: {
          data: this.barmonth,
        },
        yAxis: {},

        series: [
          {
            name: "销量",
            type: "bar",
            data: this.barnum,
            color: "#4ad2ff",
          },
        ],
      });
    },
  },
};
</script>
<style >
.myChart {
  width: 100%;
  height: 230px;
}
.title {
  font-weight: 300;
  font-size: 14px;
  margin: 0px 0px 15px 0px;
}
</style>

