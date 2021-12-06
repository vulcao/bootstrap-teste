<template>
  <div>
    <b-sidebar id="sidebar-no-header" 
      aria-labelledby="sidebar-no-header-title" 
      no-header shadow
      bg-variant="dark"
      text-variant="light"
      backdrop backdrop-variant="dark">
      <template #default="{ hide }">
        <div class="p-3">
          <div class="d-flex align-items-center flex-column">
            <b-avatar variant="primary" text="PS" class="mb-3 mt-3" size="6rem"></b-avatar>
            <h4 id="sidebar-no-header-title">Vue com Bootstrap</h4>
            <div class="divider-menu"></div>
          </div>
          <nav class="mb-3">
            <b-nav vertical>
              <b-nav-item to="/" active @click="hide"><b-icon icon="bar-chart-fill"></b-icon> Dashboard</b-nav-item>
              <b-nav-item to="/about" @click="hide"><b-icon icon="truck"></b-icon> Caminhões</b-nav-item>
              <b-nav-item to="/pessoa" @click="hide"><b-icon icon="person"></b-icon> Pessoas</b-nav-item>
            </b-nav>
          </nav>
          <b-button variant="primary" block @click="hide">Fechar</b-button>
        </div>
      </template>
    </b-sidebar>
  </div>
</template>

<script>
export default {
  name: 'SideBarComp'
}
</script>

<style scoped>
.nav-item > .nav-link {
color: #FFF;
transition: .5s;
}
.nav-item > .nav-link:hover {
color: #CCC;
}
.divider-menu {
  border: 1px solid #fff;
  width: 100%;
}
</style>
