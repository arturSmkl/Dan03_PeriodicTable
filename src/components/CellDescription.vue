<script setup>

</script>

<template>
  <div class="outer-container"  style="gridArea: 2 / 3 / 3 / 4">
    <div class="inner-container">
      <p>
        Atomic
      </p>
      <p class="symbol">
        Symbol
      </p>
      <p>
        Name
      </p>
      <p>
        Atomic mass
      </p>
    </div>
  </div>
</template>

<style scoped>
.outer-container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.inner-container {
  width: 76px;
  aspect-ratio: 1/1;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: start;
  border-radius: 6px;
  padding: 0.3rem;
}

.symbol {
  font-size: 1.4rem;
  font-weight: bold;
  line-height: 1.5;
}
</style>