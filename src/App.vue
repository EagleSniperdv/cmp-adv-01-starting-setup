<template>
  <div>
    <the-header></the-header>
      <button @click="setSelectedComponent('active-goals')">Active Goals</button>
      <button @click="setSelectedComponent('manage-goals')">Manage Goals</button>
    <!-- <am-button></am-button> -->
    <!-- <active-goals v-if="selectedComponent === 'active-goals'"></active-goals> -->
    <!-- <manage-goals v-if="selectedComponent === 'manage-goals'"></manage-goals> -->
    <!-- <badge-list></badge-list>
    <user-info
      :full-name="activeUser.name"
      :info-text="activeUser.description"
      :role="activeUser.role"
    ></user-info>
    <course-goals>
      <template #default="slotprops">
        <h2>{{ slotprops.item }}</h2>
      </template>
    </course-goals> -->
    <keep-alive>
      <component :is="selectedComponent"></component>
    </keep-alive>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
// import BadgeList from './components/BadgeList.vue';
// import UserInfo from './components/UserInfo.vue';
// import CourseGoals from './components/CourseGoals.vue';
import ActiveGoals from './components/ActiveGoals.vue';
import ManageGoals from './components/ManageGoals.vue';
// import AmButton from './components/AmButton.vue';

export default {

  components: {
    TheHeader,
    ActiveGoals,
    ManageGoals,
    // AmButton
    // BadgeList,
    // UserInfo,
    // CourseGoals
  },

  data() {
    return {

      selectedComponent: 'active-goals',

      activeUser: {
        name: 'Maximilian Schwarzmüller',
        description: 'Site owner and admin',
        role: 'admin',
      },
    };
  },

  methods: {
    setSelectedComponent(cmp) {
      this.selectedComponent = cmp;
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