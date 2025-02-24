<template>
  <div class="min-h-screen bg-gray-100">
    <div class="container mx-auto px-4 py-8 space-y-8">
      <h1 class="text-3xl font-bold text-gray-900 mb-8">
        Table Examples
      </h1>

      <!-- Users Table -->
      <div>
        <h2 class="text-xl font-semibold text-gray-800 mb-4">Team Members</h2>
        <BaseTable :tableData="usersData" />
      </div>

      <!-- Products Table -->
      <div>
        <h2 class="text-xl font-semibold text-gray-800 mb-4">Product Inventory</h2>
        <BaseTable :tableData="productsData" />
      </div>
    </div>
  </div>
</template>

<script>
import BaseTable from './components/BaseTable.vue'

export default {
  name: 'App',
  components: {
    BaseTable
  },
  data() {
    return {
      usersData: {
        headers: ['Name', 'Role', 'Department', 'Status', 'Join Date'],
        rows: [
          ['John Doe', 'Senior Developer', 'Engineering', 'Active', '2023-01-15'],
          ['Sarah Smith', 'UX Designer', 'Design', 'Active', '2023-03-22'],
          ['Mike Johnson', 'Product Manager', 'Product', 'On Leave', '2022-11-30'],
          ['Lisa Brown', 'Data Analyst', 'Analytics', 'Active', '2023-06-01']
        ]
      },
      productsData: {
        headers: ['Product Name', 'Category', 'Price', 'Stock', 'Last Updated'],
        rows: [
          ['MacBook Pro', 'Electronics', '$1299.99', '45 units', '2024-01-10'],
          ['Wireless Mouse', 'Accessories', '$49.99', '122 units', '2024-01-15'],
          ['27" Monitor', 'Electronics', '$399.99', '18 units', '2024-01-12'],
          ['USB-C Cable', 'Accessories', '$19.99', '234 units', '2024-01-14']
        ]
      }
    }
  }
}
</script> 