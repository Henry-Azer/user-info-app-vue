<template>
  <BaseCard>
    <template #card-header>
      <h2>Available Badges</h2>
    </template>
    
    <template v-slot:default>
      <ul>
        <li>
          <BaseBadge type="admin" caption="ADMIN" />
        </li>
        <li>
          <BaseBadge type="author" caption="AUTHOR" />
        </li>
      </ul>
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

};

</script>

<style>
section h2 {
  margin: 0.5rem 0;
  color: #3a3a3a;
} 

ul {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: row;
}

li {
  margin-right: 1rem;
}
</style>