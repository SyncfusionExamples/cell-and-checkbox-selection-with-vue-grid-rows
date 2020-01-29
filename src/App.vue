<template>
  <div id="app">
    <!-- Include this :selectedRowIndex=3 in below below grid code to select row on initial rendering  -->
    <!-- Include this :rowSelected="rowSelected" in below code to get selected row indexes -->
    <ejs-grid ref="grid"
      :dataSource="data"
      :selectionSettings="selectionOptions">
      <e-columns>
        <!-- Uncomment below code to enable checkbox in grid row -->
        <!-- <e-column type="checkbox" width="50"></e-column> -->
        <e-column field="OrderID" headerText="Order ID" textAlign="Right"></e-column>
        <e-column field="CustomerID" headerText="Customer ID"></e-column>
        <e-column field="ShipCity" headerText="ShipCity"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry"></e-column>
      </e-columns>
    </ejs-grid>
  </div>
</template>

<script>

import Vue from "vue";
import { GridPlugin } from "@syncfusion/ej2-vue-grids";
import { data } from "./dataSource";

Vue.use(GridPlugin);

export default {
  data() {
    return {
      data: data,
      selectionOptions: {
        type: "Multiple",
        mode: "Cell",
        cellSelectionMode: 'Box',
        //enableToggle: false
        //checkboxOnly: true,
        //checkboxMode: "ResetOnRowClick"
      }
    };
  },
  methods: {
    //Uncomment below code to get selected row indexes
    // rowSelected(){
    //   var gridInst = this.$refs.grid;
    //   if(gridInst){
    //     alert(gridInst.getSelectedRowIndexes());
    //   }
    // }
  }
};
</script>

<style>
@import url("https://cdn.syncfusion.com/ej2/material.css");
</style>
