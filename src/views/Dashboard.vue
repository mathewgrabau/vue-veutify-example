<template>
  <div>
    <h1>Dashboard</h1>
    <v-data-table
      :headers="headers"
      :items="employees"
      :items-per-page="5"
      class="elevation-1"
      @click:row="selectRow"
      multi-sort
    ></v-data-table>
    <div class="text-center ma-2">
      <v-snackbar v-model="snackbar">
        You have selected {{ currentItem }}
        <v-btn color="pink" text @click="snackbar = false">
          Close
        </v-btn>
      </v-snackbar>
    </div>
  </div>
</template>

<script>
import tableData from '../data/employees.json'

export default {
  data() {
    return {
      snackbar: false,
      currentItem: '',
      headers: [
        {
          text: 'ID',
          align: 'start',
          sortable: true,
          value: 'id'
        },
        { text: 'Name', value: 'name' },
        { text: 'Title', value: 'title' },
        { text: 'Salary', value: 'salary' }
      ],
      employees: tableData
    }
  },
  methods: {
    selectRow(event) {
      this.snackbar = true
      this.currentItem = `${event.name} - ${event.title}`
    }
  }
}
</script>

<style></style>
