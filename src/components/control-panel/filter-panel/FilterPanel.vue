<template>
  <div class="filter-panel flex-6 flexbox flexdir-col">
    <h2 class="filter-panel-title">Filters</h2>
    <div class="filter-panel-group-wrapper flex-1 flexbox flexdir-col">
      <FilterInput
        v-for="(filter, index) in filters"
        :key="index"
        :filter="filter"
        :index="index"
        class="flex-1"
      >
      </FilterInput>
    </div>
  </div>
</template>

<script>
import FilterInput from "./FilterInput.vue";
export default {
  components: {
    FilterInput,
  },
  computed: {
    filters() {
      return this.$store.getters.getFilters;
    },
  },
};
</script>

<style scoped>
.filter-panel {
  color: #240046;
  padding: 0.5rem 1rem;
  border-top: 3px solid rgb(44, 42, 42);
  margin-bottom: 0.1rem;
}
.filter-panel-title {
  font-weight: 500;
  font-size: 180%;
  margin-bottom: 0.4rem;
  font-weight: bolder;
}
</style>
