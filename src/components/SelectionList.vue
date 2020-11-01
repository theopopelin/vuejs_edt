<template>
  <div class="container w-4/5 mx-auto mt-4">
    <h1 class="text-lg font-bold">Mes cours</h1>

    <div v-if="selection.length == 0">
      <p>Aucun cours sélectionné</p>
    </div>
    <div v-else>
      <div
        v-for="cours in selection"
        :key="cours.name"
        class="border border-gray-400 my-4 p-2 rounded"
      >
        <h3 class="font-bold py-2 px-1">{{ cours.name }} avec {{ cours.teacher }}</h3>
        <span class="px-3" >{{ cours.time }} heures</span>
      </div>
    </div>

  </div>
  
</template>

<script>
export default {
  name: "selection-list",
  props: ['selection'],
  computed: {

  }


}
</script>

<style>

</style>