<script setup lang="ts">
import { ref } from 'vue';

defineProps<{ msg: string; hasNested?: boolean }>();

const emits = defineEmits<{
  (eventName: 'foo', value: number | undefined): void;
}>();

function handleFoo(bar?: number) {
  console.log('bar', bar);
}

function handleClick() {
  emit('foo');
}
</script>

<template>
  <p>{{ msg }}</p>
  <button @click="handleClick">Click me</button>
  <hr />
  <HelloWorld v-if="hasNested" @foo="handleRandom" />
</template>
