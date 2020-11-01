<template>
  <div 
    class="border m-2 p-2 flex justify-between"
    :class="cancelStyle"
  >
    <div>
      <h1 class="text-lg font-bold">{{ cours.name }}</h1>
      <p> {{ cours.teacher }}<br>{{ cours.time }} heures</p>
    </div>

    <base-button  v-if="this.isCancelled == false"
      text="Sélectionner"
      @click="addToSelection"
    >
    </base-button>
    <base-button  v-else
                  text="Indisponible"
    >
    </base-button>

  </div>
</template>

<script>
export default {
  name: "cours-card",
  props: ['cours'],
  computed: {

    isCancelled() {
      if(this.cours.cancelled == "yes"){
        return true
      }
      return false
    },
    cancelStyle() {
      return {
        'bg-red-500': this.isCancelled,
        'border-white': this.isCancelled
      }
    }
  },
  methods: {
    addToSelection() {
      this.$emit('add-cours', this.cours)
    }
  }
}
</script>

<style scoped>

</style>