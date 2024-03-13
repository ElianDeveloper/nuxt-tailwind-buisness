<script>
import { Pie } from "vue-chartjs";
import {
  Chart as ChartJS,
  Title,
  Tooltip,
  Legend,
  ArcElement,
  CategoryScale,
} from "chart.js";

ChartJS.register(Title, Tooltip, Legend, ArcElement, CategoryScale);

const data = {
  labels: ["Expenses", "Sells"],
  datasets: [
    {
      backgroundColor: ["#41B883", "#E46651"],
      data: [12345.67, 8901.23],
    },
  ],
};

const options = {
  responsive: true,
  maintainAspectRatio: false,
};

export default {
  name: "Chart",
  components: { Pie },
  data() {
    return {
      chartData: data,
      chartOptions: options,
    };
  },
};
</script>

<template>
  <div
    class="flex flex-col justify-center items-center w-full h-auto bg-white rounded-lg shadow-lg p-3"
  >
    <div class="text-2xl font-bold mb-2">Percentage of Sales and Expenses</div>
    <div class="w-full h-full">
      <Pie id="my-chart-id" :options="chartOptions" :data="chartData" />
    </div>
  </div>
</template>
