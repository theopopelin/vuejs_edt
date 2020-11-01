<template>
  <button class="btn-black">
    {{ text }}
  </button>
</template>

<script>
export default {
  props: ['text']
}
</script>

<style scoped>
.btn-black {
  @apply bg-blue-500 text-white font-bold py-2 px-4 rounded;
}
.btn-black:hover {
  @apply bg-black;
}
</style>