<script setup>
const props = defineProps({
  gridArea: {
    type: String,
    required: true
  },
})

const gridArea = `grid-area: ${props.gridArea}`
</script>

<template>
<div class="container" :style="gridArea">
  <div class="row">
    <div class="box">
      <p style="color: var(--white-mute);">
        C
      </p>
    </div>
    <p>
      Solid
    </p>
  </div>
  <div class="row">
    <div class="box">
      <p style="color: var(--rose);">
        H
      </p>
    </div>
    <p>
      Gas
    </p>
  </div>
  <div class="row">
    <div class="box">
      <p style="color: var(--sea);">
        Hg
      </p>
    </div>
    <p>
      Liquid
    </p>
  </div>
</div>
</template>

<style scoped>

.container {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: stretch;
}

.row {
  display: flex;
  justify-content: start;
  align-items: center;
}

.box {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 3.5rem;
  aspect-ratio: 1 / 1;
  margin-right: 1rem;
  border-radius: 6px;
  background-color: var(--dust-trans);
  border: 0.15rem solid var(--dust);
}

.row p {
  font-weight: bold;
  font-size: 1.2rem;
}

.box p {
  font-size: 1.5rem;
}

</style>