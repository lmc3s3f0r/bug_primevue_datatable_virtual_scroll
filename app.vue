<template>
  <div>
    <DataTable
      scrollable
      scrollHeight="400px"
      :virtualScrollerOptions="{ itemSize: 10 }"
      :value="rows ?? []"
    >
      <Column
        v-for="col of columns"
        :key="col.field"
        :field="col.field"
        :header="col.header"
        :column-key="col.field"
        class="cell-content text-nowrap"
      >
        <template #body="{ data, field }">
          <div>
            {{ data[field] }}
            {{ col.unit }}
          </div>
        </template>
      </Column>
    </DataTable>
    TOTAL ROWS: {{ rows.length }}
  </div>
</template>

<script setup lang="ts">
import { columns, rows } from "./assets/config/config";

const cars = ref();
const date = ref();
</script>

<style>
.p-datatable-table {
  width: 100%;
}

.cell-content {
  padding: 12px;
}

.p-column-header-content {
  background-color: #dd9999;
}
</style>
