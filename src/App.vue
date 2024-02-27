<template>
  <div>
    <the-header></the-header>
    <button @click="setSelectedComponent('active-goals')">Set active goals</button>
    <button @click="setSelectedComponent('manage-goals')">Set manage goals</button>
    <component :is="selectedComponent"></component>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import ActiveGoals from './components/ActiveGoals.vue';
import ManageGoals from './components/ManageGoals.vue';

export default {
  components: {
    TheHeader,
    ActiveGoals,
    ManageGoals
  },
  data() {
    return {
      activeUser: {
        name: 'Maximilian SchwarzmÃžller',
        description: 'Site owner and admin',
        role: 'admin',
      },
      selectedComponent: 'active-goals',
    };
  },
  methods: {
    setSelectedComponent(cpn) {
      this.selectedComponent = cpn;
    }
  }
};
</script>

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>