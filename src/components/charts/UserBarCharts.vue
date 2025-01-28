<template>
  <div class="graph">
    <div class="graph-header">
      <h2 class="graph-title">User Stat</h2>
      <div class="graph-buttons">
        <button class="graph-button" :class="{ active: currentGraphIndex === 0 }" @click="currentGraphIndex = 0">
          Month
        </button>
        <button class="graph-button" :class="{ active: currentGraphIndex === 1 }" @click="currentGraphIndex = 1">
          6 Month
        </button>
        <button class="graph-button" :class="{ active: currentGraphIndex === 2 }" @click="currentGraphIndex = 2">
          Year
        </button>
      </div>
    </div>
    <canvas ref="chartCanvas"></canvas>
  </div>
</template>

<script>
import { Chart, registerables } from "chart.js";
Chart.register(...registerables);
Chart.defaults.backgroundColor = "#2563EB";
Chart.defaults.barThickness = 12;
export default {
  data() {
    return {
      currentGraphIndex: 0,
      chart: null,
      graphData: [
        {
          labels: [
            "",
            "2",
            "",
            "4",
            "",
            "6",
            "",
            "8",
            "",
            "10",
            "",
            "12",
            "",
            "14",
            "",
            "16",
            "",
            "18",
          ],
          datasets: [
            {
              label: "Dataset 1",
              borderSkipped: "bottom",
              barPersentage: 0.5,
              borderRadius: 100,
              data: [
                334, 23, 132, 510, 232, 430, 603, 301, 777, 111, 132, 510, 232,
                430, 63, 301, 47, 201,
              ],
            },
          ],
        },
        {
          labels: [
            "",
            "2",
            "",
            "4",
            "",
            "6",
            "",
            "8",
            "",
            "10",
            "",
            "12",
            "",
            "14",
            "",
            "16",
            "",
            "18",
          ],
          datasets: [
            {
              label: "Dataset 2",
              borderSkipped: "bottom",
              barPersentage: 0.5,
              borderRadius: 100,
              data: [
                234, 723, 132, 510, 232, 430, 603, 301, 777, 111, 132, 510, 232,
                430, 603, 301, 477, 111,
              ],
            },
          ],
        },
        {
          labels: [
            "",
            "2",
            "",
            "4",
            "",
            "6",
            "",
            "8",
            "",
            "10",
            "",
            "12",
            "",
            "14",
            "",
            "16",
            "",
            "18",
          ],
          datasets: [
            {
              label: "Dataset 3",
              borderSkipped: "bottom",
              barPersentage: 0.5,
              borderRadius: 100,
              data: [
                634, 723, 132, 710, 232, 432, 203, 301, 177, 311, 132, 510, 232,
                230, 203, 501, 177, 311,
              ],
            },
          ],
        },
      ],
    };
  },
  watch: {
    currentGraphIndex() {
      this.updateChart();
    },
  },
  mounted() {
    Chart.register(...registerables);
    this.renderChart();
  },
  methods: {
    renderChart() {
      const ctx = this.$refs.chartCanvas.getContext("2d");
      this.chart = new Chart(ctx, {
        type: "bar",
        data: this.graphData[this.currentGraphIndex],
        options: {
          animation: true,
          responsive: true,
          scales: {
            y: {
              position: "right",
              grid: {
                display: false,
              },
              border: {
                display: false,
              },
            },
            x: {
              grid: {
                display: false,
              },
            },
          },
          plugins: {
            tooltip: {
              fontSize: 30,
              callbacks: {
                title: function (context) {
                  const value = `${context.raw}`;
                  return `Useers: ${value}`;
                },
              },
              caretPadding: 5,
              cornerRadius: 10,
              multiKeyBackground: "#000",
              displayColors: false,
              backgroundColor: "#fff",
              titleColor: "#000",
              borderColor: "#DADEE6",
              borderWidth: 1,
              titleAlign: "center",
            },
            legend: {
              display: false,
            },
          },
        },
      });
    },
    updateChart() {
      if (this.chart) {
        this.chart.destroy();
      }
      this.renderChart();
    },
  },
};
</script>

<style scoped lang="scss">
.graph {
  width: 56rem;
  height: 35rem;
  border-radius: 1.2rem;
  border: #e0e0e0 0.1rem solid;
  &-title {
      font-size: 1.6rem;
      font-weight: bold;
      color: #333;
      margin: 0;
    }
  &-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 2rem 2.6rem;
    border-bottom: #e0e0e0 0.1rem solid;
  }
  &-buttons{
    display: flex;
    gap: 1rem;
  }
  &-button {
    height: 3rem;
    padding: 0rem 1.2rem;
    border: rgba(37, 99, 235, 1) .1rem solid;
    color: rgba(37, 99, 235, 1);
    border-radius: .5rem;
    font-size: 1.6rem;
    cursor: pointer;
  }
  & canvas {
    padding: 3rem;
    width: 100%;
    width: 100%;
    aspect-ratio: unset;
  }
}
.active{
    background: rgba(37, 99, 235, 1);
    color: #fff;
}
@media (max-width: 480px) {
  .graph{
    &-title{
      font-size: 1.2rem;
    }
    & canvas{
      padding: 2rem;
    }
    &-buttons{
      gap: .3rem
    }
    &-button{
      height: 2.5rem;
      font-size:1.4rem;
    }
  }
}
</style>
