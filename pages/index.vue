<template>
  <div>
    <NavBar />
  </div>
  <div
    class="bg-gray-100 min-h-screen flex flex-col items-center justify-center"
  >
    <h1 class="text-4xl font-bold text-gray-800 mb-4">Welcome to your Store</h1>
    <p class="text-lg text-gray-600 mb-8">
      Here you can manage your sales, expenses and obtain valuable information
      about your business.
    </p>
    <div class="flex justify-center gap-4 flex-row">
      <div class="w-full md:w-1/2 p-4 bg-white rounded-lg shadow-md">
        <h2 class="text-lg font-bold text-gray-800 mb-2">Sales Day</h2>
        <div class="flex flex-col items-center justify-center">
          <span class="text-2xl font-bold text-gray-800">
            $ {{ totalSales }}</span
          >
          <p class="text-sm text-gray-600">Total sales</p>
        </div>
        <div class="mt-4"></div>
      </div>

      <div class="w-full md:w-1/2 p-4 bg-white rounded-lg shadow-md">
        <h2 class="text-lg font-bold text-gray-800 mb-2">Expenses Day</h2>
        <div class="flex flex-col items-center justify-center">
          <span class="text-2xl font-bold text-gray-800">
            $ {{ totalExpenses }}</span
          >
          <p class="text-sm text-gray-600">Total expense</p>
        </div>
        <div class="mt-4"></div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      totalSales: 0,
      totalExpenses: 0,
      salesData: [],
      expensesData: [],
      data: [10, 20, 30, 40, 50],
      labels: ["A", "B", "C", "D", "E"],
    };
  },
  mounted() {
    const salesData = [
      100, // Sale 1 amount
      150, // Sale 2 amount
      200, // Sale 3 amount
    ];

    this.totalSales = salesData.reduce((acc, sale) => acc + sale, 0);

    const expensesData = [
      50, // Expense 1 amount
      75, // Expense 2 amount
      125, // Expense 3 amount
    ];

    this.totalExpenses = expensesData.reduce(
      (acc, expense) => acc + expense,
      0
    );

    // this.salesData = salesData;
    // this.expensesData = expensesData;
  },
};
</script>
