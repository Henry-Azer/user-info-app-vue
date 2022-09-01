<template>
  <div>
    <h2>Active Goals</h2>
    <input type="text" ref="goal" />
    <button @click="setGoal">Set Goal</button>

    <teleport to="#app">
      <ErrorAlert v-if="isInputInValid">
        <p>Input is Invalid, must not be empty</p>
        <button @click="confirmError">Okay</button>
      </ErrorAlert>
    </teleport>
  </div>
</template>

<script>
import ErrorAlert from "./ErrorAlert";

export default {
  components: {
    ErrorAlert,
  },

  data() {
    return {
      isInputInValid: false,
    };
  },
  methods: {
    setGoal() {
      const value = this.$refs.goal.value;
      if (value === "") this.isInputInValid = true;
    },
    confirmError() {
      this.isInputInValid = false;
    },
  },
};
</script>