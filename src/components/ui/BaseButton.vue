<script setup>
import { computed } from "vue";

// Props for customization
const props = defineProps({
  label: String,
  size: { type: String, default: "md" }, // sm, md, lg
  variant: { type: String, default: "primary" }, // primary, secondary, outline
  icon: String, // Optional icon (if using Heroicons)
  disabled: Boolean,
});

// Size classes
const sizeClasses = {
  sm: "px-3 py-1 text-sm",
  md: "px-4 py-2 text-base",
  lg: "px-6 py-3 text-lg",
};

// Variant classes
const variantClasses = {
  primary: "bg-white text-black hover:bg-gray-100 border rounded-xl",
  secondary: "bg-gray-600 text-white hover:bg-gray-700",
  outline: "border border-gray-600 text-gray-600 hover:bg-gray-100",
};

// Compute final button classes
const buttonClasses = computed(
  () => `
  flex items-center justify-center gap-2 rounded-md font-medium transition
  ${sizeClasses[props.size] || sizeClasses.md}
  ${variantClasses[props.variant] || variantClasses.primary}
  ${props.disabled ? "opacity-50 cursor-not-allowed" : ""}
`
);
</script>

<template>
  <button :class="buttonClasses" :disabled="disabled">
    <component v-if="icon" :is="icon" class="w-5 h-5" />
    <span>{{ label }}</span>
  </button>
</template>
