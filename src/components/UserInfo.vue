<template>
  <BaseCard>
    <template v-slot:card-header>
      <h3>{{ fullName }}</h3>
      <BaseBadge :type="role" :caption="role.toUpperCase()" />
    </template>

    <template v-slot:default>
      <p>{{ infoText }}</p>
    </template>
  </BaseCard>
</template>

<script>
import BaseBadge from './BaseBadge';
import BaseCard from './BaseCard';

export default {

  components: {
    BaseBadge, BaseCard,
  },

  props: ['fullName', 'infoText', 'role'],

};
</script>

<style>
section div {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>