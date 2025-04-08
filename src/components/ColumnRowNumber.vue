<script setup>
const props = defineProps({
  columnStart: {
    type: Number,
    required: true
  },
  rowStart: {
    type: Number,
    required: true
  },
  columnRowNumber: {
    type: Number,
    required: true
  }
})

const gridArea = `grid-area: ${props.rowStart} / ${props.columnStart} / ${props.rowStart + 1} / ${props.columnStart + 1}`

</script>

<template>
<div class="container" :style=gridArea>
  <p>
    {{ columnRowNumber }}
  </p>
</div>
</template>

<style scoped>

.container {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

p {
  font-size: 2rem;
  font-weight: bold;
}

</style>