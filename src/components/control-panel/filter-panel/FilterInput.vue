<template>
  <div class="filter-input">
    <div class="flex flexbox flexbox-space-between">
      <label :for="filter.name"> {{ filter.name }}</label>
      <span> {{ filter.current }}%</span>
    </div>

    <input
      v-model="filter.current"
      @mousemove="updateFilterValue(filter)"
      @change="updateFilterValue(filter)"
      :id="filter.name"
      :min="filter.min"
      :max="filter.max"
      class="filter-range"
      type="range"
    />
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  props: ["filter", "index"],
  methods: {
    ...mapActions(["setFilterValue_STORE"]),
    updateFilterValue(filter) {
      //console.log(this.index);
      const payload = {
        index: this.index,
        filterNewValue: filter.current,
      };
      this.setFilterValue_STORE(payload);
      //console.log(filter.name,`${filter.current}${filter.suffix}`);
    },
  },
};
</script>

<style scoped>
label {
  color: var(--colblack);
  display: block;
  font-size: 110%;
  margin-bottom: 0.1rem;
}
.filter-range {
  width: 100%;
}
</style>
