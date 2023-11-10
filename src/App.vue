<template>
  <div>
    <DashboardLayout />
  </div>
</template>

<script>
import DashboardLayout from './components/DashboardLayout.vue';

export default {
  name: 'App',
  components: {
    DashboardLayout
  }
}
</script>

<style>
:root {
  --main-color: #2d3035;
  --background-color: #111b21;
  --secundary-color: #8a8d93;
  --light-color: #f2f2f2;
  --second-light-color: #ccc;

  --safe-priority: #5cb85c;
  --medium-priority: #f0ad4e;
  --danger-priority: #d9534f;
  --primary-priority: #0275d8;
  --info-priority: #5bc0de;
}

/*Main Setting */

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Open Sans", sans-serif;
}

body {
  background-color: #111b21;
  margin: 2em;
  scrollbar-width: none;
  -ms-overflow-style: none;
}

body::-webkit-scrollbar {
  width: 0;
  background-color: transparent;
}

/* Priorities */

#urgent {
  background-color: var(--danger-priority);
}

#medium {
  background-color: var(--medium-priority);
}

#safe {
  background-color: var(--safe-priority);
}

/* Icons */

.fa-star {
  color: var(--safe-priority);
}

.fa-user {
  color: var(--primary-priority);
}

.fa-clock {
  color: var(--medium-priority);
}

.fa-solid {
  font-size: 2em;
}
</style>
