<script setup>
const props = defineProps({
  gridArea: {
    type: String,
    required: true
  },
  colorClass: {
    type: String,
    required: true
  },
  range: {
    type: String,
    required: true
  },
})

const gridArea = `grid-area: ${props.gridArea}`;

</script>

<template>
<div class="container" :style="gridArea">
  <p :class="colorClass">
    {{ props.range }}
  </p>
</div>
</template>

<style scoped>

.container {
  display: flex;
  justify-content: center;
  align-items: center;
}

p {
  font-size: 1.5rem;
  font-weight: bold;
  text-align: center;
  padding: 0.5rem;
  border-radius: 6px;
}

.beige {
  background-color: var(--beige-trans);
}

.magenta {
  background-color: var(--magenta-trans);
}

</style>