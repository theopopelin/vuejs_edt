<template>

  <div class="flex">
    <div class="w-1/5">
      <selection-box
        :selection="selection"
      >

      </selection-box>
      <span class="font-bold py-2 px-4 " style="padding: 50px">Total : {{ calcheures() }} Heures</span>


    </div>
    

    <div class="w-4/5 mt-2">
      <cours-card
        v-for="(cours, index) in ttbl.cours"
        :key="index"
        :cours="cours"
        @add-cours="addCoursToSelection"
        >
      </cours-card>
    </div>

  </div>

</template>

<script>
import ttblData from '../data/cours.json'
import CoursCard from './CoursCard.vue'
import SelectionBox from './SelectionBox.vue'
export default {
  name: "cours-view",
  components: {
    CoursCard,
    SelectionBox
  },
  data() {

    return {
      ttbl: ttblData,
      selection: [],
      total:[],
    }
  },
  methods: {
    addCoursToSelection(cours){
      this.selection.push(cours)
      this.total.push(cours.time)
      this.$emit('child-event', cours)
    },

    calcheures() {
      let numberArray = this.total.map(Number)
      var sum = numberArray.reduce(function(a, b){
        return a + b;
      }, 0);
      return sum;
    }

  }

}
</script>

<style scoped>

</style>