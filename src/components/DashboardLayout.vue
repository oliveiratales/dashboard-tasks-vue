<template>
  <div class="dashboard">
    <MainTable />
    <SidebarLayout />
  </div>
</template>

<script>
import SidebarLayout from './SidebarLayout.vue';
import MainTable from './MainTable.vue';

export default {
  name: 'DashboardLayout',
  components: {
    SidebarLayout,
    MainTable
  }
}
</script>

<style>
.dashboard {
  display: flex;
  gap: 1em;
  min-width: 1600px;
}
</style>
