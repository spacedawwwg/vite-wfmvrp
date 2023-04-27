<script setup lang="ts">
import { ref } from 'vue';

defineProps<{ msg: string; hasNested?: boolean }>();

const emit = defineEmits<{
  (eventName: 'foo', value: number | undefined): void;
}>();

function handleFoo(bar?: number) {
  window.alert(bar);
}

function handleClick() {
  emit('foo', Math.random());
}
</script>

<template>
  <p>{{ msg }}</p>
  <button @click="handleClick">Click me</button>
  <hr />
  <HelloWorld v-if="hasNested" @foo="handleFoo" />
</template>
