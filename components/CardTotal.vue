<template>
  <div
    class="flex flex-col justify-center items-center w-full h-48 bg-white rounded-lg shadow-lg"
  >
    <div class="text-2xl font-bold mb-2">Totals for the Day</div>
    <div class="flex flex-row justify-between w-full">
      <div class="flex flex-col items-center w-1/2">
        <span class="text-xl font-bold">Sells:</span>
        <span class="text-green-500 text-2xl font-bold">{{ totalVentas }}</span>
      </div>
      <div class="flex flex-col items-center w-1/2">
        <span class="text-xl font-bold">Expenses:</span>
        <span class="text-red-500 text-2xl font-bold">{{ totalGastos }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    totalVentas: {
      type: Number,
      required: true,
    },
    totalGastos: {
      type: Number,
      required: true,
    },
  },
};
</script>
