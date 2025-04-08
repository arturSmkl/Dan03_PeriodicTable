<script setup>
const props = defineProps({
  gridArea: {
    type: String,
    required: true
  }
})

const gridArea = `grid-area: ${props.gridArea}`

const categories = [
  {
    name: "Alkali Metals",
    bgStyle: "background-color: var(--sunrise-trans)",
  },
  {
    name: "Alkaline Earth Metals",
    bgStyle: "background-color: var(--sunglow-trans)",
  },
  {
    name: "Transition Metals",
    bgStyle: "background-color: var(--red-crayola-trans)",
  },
  {
    name: "Post Transition Metals",
    bgStyle: "background-color: var(--sky-trans)",
  },
  {
    name: "Lanthanoids",
    bgStyle: "background-color: var(--beige-trans)",
  },
  {
    name: "Actinoids",
    bgStyle: "background-color: var(--magenta-trans)",
  },
  {
    name: "Metalloids",
    bgStyle: "background-color: var(--turquoise-trans)",
  },
  {
    name: "Reactive Nonmetals",
    bgStyle: "background-color: var(--jade-trans)",
  },
  {
    name: "Noble Gases",
    bgStyle: "background-color: var(--indigo-trans)",
  },
]

</script>

<template>
  <div class="outer-container" :style="gridArea">
    <div class="blocks-container">
      <div class="block" v-for="c in categories" :style="c.bgStyle">
        <p>
          {{ c.name }}
        </p>
      </div>
    </div>
    <div class="groups-container">
      <div class="group group-1">
        <p>
          Metals
        </p>
      </div>
      <div class="group group-2">
        <p>
          Nonmetals
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>

.outer-container {
  height: 81%;
  display: flex;
  justify-content: space-between;
  align-items: stretch;
}

.blocks-container {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: stretch;
  width: 70%;
  height: 100%;
}

.block {
  width: 100%;
  height: 95%;
  display: flex;
  justify-content: end;
  align-items: center;
  margin: 0.1rem 0;
  padding-right: 0.5rem;
  border-radius: 6px;
}

.block p {
  font-size: 1.1rem;
  font-weight: bold;
}

.groups-container {
  width: 30%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: stretch;
}

.group {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  border-top-right-radius: 6px;
  border-bottom-right-radius: 6px;
  border: 0.1rem solid var(--dust);
  border-left: none;
}

.group-1 {
  height: 66.66%
}

.group-2 {
  height: 22.22%;
}

</style>