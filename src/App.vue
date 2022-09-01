<template>
  <div>
    <Header />

    <BadgeList />
    <UserInfo
      :full-name="activeUser.name"
      :info-text="activeUser.description"
      :role="activeUser.role"
    />
    <CourseGoals>
      <template #default="slotProps">
        <h2>{{ slotProps.goal }}</h2>
      </template>
    </CourseGoals>

    <div>
      <button @click="setSelectedComponent('ActiveGoals')">Active Goals</button>
      <button @click="setSelectedComponent('ManageGoals')">Manage Goals</button>

      <keep-alive>
        <component :is="selectedComponent"></component>
      </keep-alive>
    </div>

    <!-- <div>
      <button @click="setSelectedComponent2('active-goals')">
        Active Goals
      </button>
      <button @click="setSelectedComponent2('manage-goals')">
        Manage Goals
      </button>

      <ActiveGoals v-if="selectedComponent2 == 'active-goals'" />
      <ManageGoals v-if="selectedComponent2 == 'manage-goals'" />
    </div> -->
  </div>
</template>
 

<script>
import Header from "./components/TheHeader";
import ActiveGoals from "./components/ActiveGoals";
import ManageGoals from "./components/ManageGoals";
import BadgeList from "./components/BadgeList";
import UserInfo from "./components/UserInfo";
import CourseGoals from "./components/CourseGoals.vue";

export default {
  components: {
    Header,
    ActiveGoals,
    ManageGoals,
    BadgeList,
    UserInfo,
    CourseGoals,
  },

  methods: {
    setSelectedComponent(component) {
      this.selectedComponent = component;
    },
    setSelectedComponent2(component) {
      this.selectedComponent2 = component;
    },
  },

  data() {
    return {
      selectedComponent: "ActiveGoals",
      selectedComponent2: "active-goals",
      activeUser: {
        name: "Maximilian Schwarzmüller",
        description: "Site owner and admin",
        role: "admin",
      },
    };
  },
};
</script>


<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}

* {
  text-align: center;
}
</style>