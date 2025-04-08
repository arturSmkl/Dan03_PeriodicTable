<script setup>
import PeriodicElement from "@/components/PeriodicElement.vue";
import ColumnRowNumber from "@/components/ColumnRowNumber.vue";
import data from "/src/assets/PeriodicTableJSON.json"
import CellDescription from "@/components/CellDescription.vue";
import RangeDescription from "@/components/RangeDescription.vue";
import PhaseDescription from "@/components/PhaseDescription.vue";
import CategoriesDescription from "@/components/CategoriesDescription.vue";

const periodicElements = []
for (let i = 0; i < 118; i++) {
  periodicElements.push(Object.values(data.elements).find(item => item.number === i+1))
}

</script>

<template>
  <div class="periodic-table">
    <!-- Column and Row Numbers -->
    <ColumnRowNumber v-for="n in 18" :column-start=n+1 :row-start=1 :column-row-number=n />
    <ColumnRowNumber v-for="n in 7" :column-start=1 :row-start=n+1 :column-row-number=n />
    <ColumnRowNumber :column-start=1 :row-start=10 :column-row-number=6 />
    <ColumnRowNumber :column-start=1 :row-start=11 :column-row-number=7 />

    <!-- Periodic Elements -->
    <PeriodicElement v-for="p in periodicElements" :periodic-element-object=p />

    <!-- Table Description -->
    <CellDescription />

    <RangeDescription range="57-71" color-class="beige" grid-area="10 / 3 / 11 / 4" />
    <RangeDescription range="89-103" color-class="magenta" grid-area="11 / 3 / 12 / 4" />

    <PhaseDescription grid-area="2 / 5 / 4 / 7" />

    <CategoriesDescription grid-area="2 / 8 / 5 / 11" />

  </div>
</template>

<style scoped>
.periodic-table {
  display: grid;
  grid-template-columns: 0.5fr repeat(18, 1fr);
  grid-template-rows: 0.5fr repeat(10, 1fr);
  width: 100%;
  height: 100%;
}
</style>