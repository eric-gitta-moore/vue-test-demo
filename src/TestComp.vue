<script setup lang="ts">
import { computed } from 'vue';

const props = defineProps<{
  modelValue: string
}>()

const emit = defineEmits<{
  'update:modelValue': [value: string]
  'confirm-click': []
}>()

const value = computed({
  get: () => props.modelValue,
  set: (val) => {
    emit('update:modelValue', val)
  }
})

</script>

<template>
  <input v-model="value" />
</template>
