<script setup>
import { ref} from "vue";

const props = defineProps({
  periodicElementObject: {
    type: Object,
    required: true
  },
})

let rowStart = props.periodicElementObject.ypos+1;
let columnStart = props.periodicElementObject.xpos+1;
let rowEnd = props.periodicElementObject.ypos+2;
let columnEnd = props.periodicElementObject.xpos+2;

const gridArea = `grid-area: ${rowStart} / ${columnStart} / ${rowEnd} / ${columnEnd}`

const colorClass = ref("");

switch (props.periodicElementObject.category) {
  case "noble gas":
    colorClass.value = "noble-gas";
    break;
  case "diatomic nonmetal":
    colorClass.value = "reactive-nonmetal";
    break;
  case "polyatomic nonmetal":
    colorClass.value = "reactive-nonmetal";
    break;
  case "metalloid":
    colorClass.value = "metalloid";
    break;
  case "post-transition metal":
    colorClass.value = "post-transition-metal";
    break;
  case "transition metal":
    colorClass.value = "transition-metal";
    break;
  case "actinide":
    colorClass.value = "actinoid";
    break;
  case "lanthanide":
    colorClass.value = "lanthanoid";
    break;
  case "alkaline earth metal":
    colorClass.value = "alkaline-earth-metal";
    break;
  case "alkali metal":
    colorClass.value = "alkali-metal";
    break;
  default:
    colorClass.value = "unknown";
    break;
}

const textColorClass = ref("");

switch (props.periodicElementObject.phase) {
  case "Solid":
    textColorClass.value += "solid";
    break;
  case "Liquid":
    textColorClass.value += "liquid";
    break;
  case "Gas":
    textColorClass.value += "gas";
    break;
  default:
    textColorClass.value += " unknown-phase";
    break;
}

const tooLong = ref("");
if (props.periodicElementObject.name.length > 10) {
  tooLong.value = "too-long";
}

</script>

<template>
<div class="outer-container"  :style="gridArea">
  <div class="inner-container" :class="colorClass">
    <p>
      {{ periodicElementObject.number }}
    </p>
    <p class="symbol" :class="textColorClass">
      {{ props.periodicElementObject.symbol }}
    </p>
    <p :class="tooLong">
      {{ props.periodicElementObject.name }}
    </p>
    <p>
      {{ (props.periodicElementObject.atomic_mass).toPrecision(5) }}
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

.too-long {
  font-size: 0.85rem;
}

.noble-gas {
  background-color: var(--indigo-trans);
  border: 0.15rem solid var(--indigo);
}

.reactive-nonmetal {
  background-color: var(--jade-trans);
  border: 0.15rem solid var(--jade);
}

.metalloid {
  background-color: var(--turquoise-trans);
  border: 0.15rem solid var(--turquoise);
}

.post-transition-metal {
  background-color: var(--sky-trans);
  border: 0.15rem solid var(--sky);
}

.transition-metal {
  background-color: var(--red-crayola-trans);
  border: 0.15rem solid var(--red-crayola);
}

.actinoid {
  background-color: var(--magenta-trans);
  border: 0.15rem solid var(--magenta);
}

.lanthanoid {
  background-color: var(--beige-trans);
  border: 0.15rem solid var(--beige);
}

.alkaline-earth-metal {
  background-color: var(--sunglow-trans);
  border: 0.15rem solid var(--sunglow);
}

.alkali-metal {
  background-color: var(--sunrise-trans);
  border: 0.15rem solid var(--sunrise);
}

.unknown {
  background-color: var(--dust-trans);
  border: 0.15rem solid var(--dust);
}

</style>