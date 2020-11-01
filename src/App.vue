<template>
  <nav-bar
    @change-component="changeSelectedComponent"
  >
  </nav-bar>
  
  <keep-alive include="cours-view">
    <component 
      :is="selectedComponent"
      v-bind="currentProps"
      @child-event="selectionUpdate"
    >
    </component>
  </keep-alive>
  
</template>

<script>

import CoursView from './components/CoursView.vue'
import SelectionList from './components/SelectionList.vue'
import NavBar from './components/navigation/NavBar.vue'

export default {
  name: 'App',
  components: {
    CoursView,
    SelectionList,
    NavBar
  },
  data() {
    return {
      selectedComponent: 'cours-view',
      coursSelection: []
    }
  },
  computed: {
    currentProps() {
      if(this.selectedComponent == "selection-list"){
        return { selection: this.coursSelection }
      }
      return false
    },
  },
  methods: {
    changeSelectedComponent(value) {
      this.selectedComponent = value
    },
    selectionUpdate(value) {
      this.coursSelection.push(value)
    }
  }
}
</script>

<style>
 
</style>
