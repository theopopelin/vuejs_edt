<template>
  <div class="bg-blue-500 text-white font-bold py-2 px-4 p-2">
    <a href="#" @click="changeComponent('cours-view')">Tous les Cours</a>
    <a style="float: right" href="#" @click="changeComponent('selection-list')">Mes Cours</a>
  </div>
</template>

<script>
export default {
  name: "nav-bar",
  methods: {
    changeComponent(value) {
      this.$emit('change-component', value)
    }
  }
}
</script>

<style>

</style>