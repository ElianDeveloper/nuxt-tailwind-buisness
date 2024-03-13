<template>
  <div>
    <div class="text-center text-3xl font-bold mb-8">
      <h1>Sales and Expense Summary - {{ fechaActual }}</h1>
    </div>
    <div class="flex flex-col justify-around mt-8 gap-5">
      <CardTotal :total-ventas="totalVentas" :total-gastos="totalGastos" />
      <CardChartPie :chart-series="chartSeries" />
    </div>
  </div>
</template>

<script>
import CardTotal from "../components/CardTotal.vue";
import CardChartPie from "../components/Chart";

export default {
  components: {
    CardTotal,
    CardChartPie,
  },
  data() {
    return {
      fechaActual: new Date().toLocaleDateString(),
      totalVentas: 12345.67,
      totalGastos: 8901.23,
      chartSeries: [this.totalVentas, this.totalGastos],
    };
  },
};
</script>
