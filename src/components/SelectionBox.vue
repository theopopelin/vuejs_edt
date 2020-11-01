<template>
  <div class="border border-gray-400 text-center m-4 p-4 rounded">
    <span class="font-bold py-2 px-4 ">Selection : {{ selection.length }}
    cours</span>

    <ul>
      <li v-for="cours in selection" :key="cours.name">{{ cours.name }}</li>
    </ul>


  </div>
  
</template>

<script>
export default {
  name: "selection-box",
  props: ['selection'],

  methods: {

  }

}
</script>

<style>

</style>