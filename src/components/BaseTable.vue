<template>
  <div class="overflow-x-auto border border-gray-200 rounded-lg">
    <table class="w-full text-sm text-left text-gray-500">
      <thead class="text-xs text-gray-700 uppercase bg-gray-50 border-b border-gray-200">
        <tr>
          <th 
            v-for="header in tableData.headers" 
            :key="header"
            scope="col" 
            class="px-6 py-3"
          >
            {{ header }}
          </th>
        </tr>
      </thead>
      <tbody>
        <tr 
          v-for="(row, index) in tableData.rows" 
          :key="index"
          class="bg-white border-b border-gray-200 hover:bg-gray-50"
        >
          <td 
            v-for="(cell, cellIndex) in row" 
            :key="cellIndex"
            class="px-6 py-4"
          >
            {{ cell }}
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'BaseTable',
  props: {
    tableData: {
      type: Object,
      required: true,
      validator(value) {
        return value.headers && value.rows && 
               Array.isArray(value.headers) && 
               Array.isArray(value.rows);
      }
    }
  }
}
</script>
