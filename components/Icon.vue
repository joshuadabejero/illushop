<script setup>
import { defineProps, computed } from "vue";
import * as LucideIcons from "lucide-vue-next";

const props = defineProps({
  name: String,
  size: { type: Number, default: 24 },
  color: { type: String, default: "currentColor" },
  className: { type: String, default: "" },
});

const IconComponent = computed(() => LucideIcons[props.name]);
</script>

<template>
  <component
    :is="IconComponent"
    v-if="IconComponent"
    :size="props.size"
    :color="props.color"
    :class="['inline-block', props.className]"
  />
  <span v-else class="text-red-500">Icon not found</span>
</template>
