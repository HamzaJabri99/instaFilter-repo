<template>
  <div class="filter-input">
    <div class="flex flexbox flexbox-space-between">
      <label :for="filter.name"> {{ filter.name | capitalize }}</label>
      <span> {{ filter.current }}%</span>
    </div>

    <input
      v-model="filter.current"
      @mousemove="updateFilterValue(filter)"
      @change="updateFilterValue(filter)"
      :id="filter.name"
      :min="filter.min"
      :max="filter.max"
      class="filter-range slider"
      type="range"
    />
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  props: ["filter", "index"],
  filters: {
    capitalize: function(value) {
      if (!value) return "";

      value = value.toString();
      return value.charAt(0).toUpperCase() + value.slice(1);
    },
  },
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
.filter-input {
  padding-bottom: 10px;
}
label {
  color: var(--colblack);
  display: block;
  font-size: 115%;
  margin-bottom: 0.1rem;
  font-weight: bold;
}
span {
  font-size: 110%;
  font-weight: 600;
}
.filter-range {
  width: 100%;
}
.slidecontainer {
  width: 100%;
}

.slider {
  -webkit-appearance: none;
  width: 100%;
  height: 10px;
  background: #ffa5ff;
  outline: none;
  opacity: 0.7;
  -webkit-transition: 0.2s;
  transition: opacity 0.2s;
  border-radius: 5px;
}

.slider:hover {
  opacity: 1;
}

.slider::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background: #8304aa;
  cursor: pointer;
}

.slider::-moz-range-thumb {
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background: #04aa6d;
  cursor: pointer;
}
</style>
