<template>
  <div>
    <p class="title">招聘数据</p>
    <div class="myline"></div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      mouth: ["三月", "四月", "五月", "六月", "七月", "八月", "九月"],
      num: [
        [0, 0, 5, 8, 11, 20, 12],
        [0, 0, 3.5, 6, 7, 12, 6],
        [0, 0, 3, 3, 4, 8, 6],
      ],
    };
  },
  mounted() {
    this.drawLine();
  },
  methods: {
    drawLine() {
      // 基于准备好的dom，初始化echarts实例
      let myline = this.$echarts.init(document.querySelector(".myline"));
      // 绘制图表
      myline.setOption({
        title: {
          text: "招聘数据/月",
        },
        tooltip: {
          trigger: "axis",
        },
        legend: {
          data: ["入职数", "离职数", "稳定数"],
        },
        grid: {
          left: "3%",
          right: "4%",
          bottom: "3%",
          containLabel: true,
        },
        toolbox: {
          feature: {
            saveAsImage: {},
          },
        },
        xAxis: {
          type: "category",
          boundaryGap: false,
          data: this.month,
        },
        yAxis: {
          type: "value",
        },
        series: [
          {
            name: "入职数",
            type: "line",
            data: this.num[1],
            color: "#cf6260",
          },
          {
            name: "离职数",
            type: "line",
            data: this.num[2],
            color: "#3b4f5d",
          },
          {
            name: "稳定数",
            type: "line",
            smooth: true,
            data: this.num[3],
            color: "#6ba5ad",
          },
        ],
      });
    },
  },
};
</script>
<style >
.myline {
  width: 100%;
  height: 230px;
}
.title {
  font-weight: 300;
  font-size: 14px;
  margin: 0px 0px 15px 0px;
}
</style>

