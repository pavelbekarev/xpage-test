<script setup lang="ts">
import "./style.scss";
const props = defineProps<{ text: string; extraClasses?: string[] }>();
console.debug(props.extraClasses);
</script>

<template>
  <div
    class="learnSectionFilter"
    :class="props.extraClasses && props.extraClasses.join(' ')"
  >
    {{ text }}
  </div>
</template>
