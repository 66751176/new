<template>
  <div>
    <p class="title">学员数据</p>
    <div class="bars"></div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      barsList: [
        ["学院评定", "技术", "灵活", "综合"],
        ["叶旺", 5, 3, 7],
        ["薛永翔", 5, 3, 7],
        ["王雪刚", 5, 3, 7],
        ["任杰", 5, 3, 7],
        ["王凯", 5, 3, 7],
        ["李猛", 5, 3, 7],
      ],
    };
  },
  mounted() {
    this.drawLine();
  },
  methods: {
    drawLine() {
      // 基于准备好的dom，初始化echarts实例
      let bars = this.$echarts.init(document.querySelector(".bars"));
      bars.setOption({
        title: { text: "学员评定" },
        grid: {
          left: "5%",
          right: "5%",
          bottom: "3%",
          containLabel: true,
        },
        legend: {},
        tooltip: {},
        dataset: {
          source: this.barsList,
        },
        xAxis: { type: "category" },
        yAxis: {},
        // Declare several bar series, each will be mapped
        // to a column of dataset.source by default.
        series: [
          { type: "bar", color: "#4ad2ff" },
          { type: "bar", color: "#4a5cff" },
          { type: "bar", color: "#89ff4a" },
        ],
      });
      // 绘制图表
    },
  },
};
</script>
<style >
.bars {
  width: 100%;
  height: 230px;
}
.title {
  font-weight: 300;
  font-size: 14px;
  margin: 0px 0px 15px 0px;
}
</style>





