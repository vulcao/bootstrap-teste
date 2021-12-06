<template>
  <div id="app">
    <NavBarComp />
    <SideBarComp />
    <router-view/>
  </div>
</template>
<script>
import NavBarComp from './components/NavBarComp'
import SideBarComp from './components/SideBarComp'

export default {
  components: {
    NavBarComp,
    SideBarComp
  }
}
</script>

<style>
</style>
