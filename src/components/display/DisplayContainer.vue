<template>
  <div class="display-container flex-5 flexbox space-center">
    <DisplayImage />
    <DisplayCanvas />
  </div>
</template>

<script>
import DisplayImage from "./DisplayImage.vue";
import DisplayCanvas from "./DisplayCanvas.vue";
export default {
  components: {
    DisplayImage,
    DisplayCanvas,
  },
  computed: {
    filters() {
      return this.$store.getters.getFilters.map((filter, index) => {
        return {
          name: filter.name,
          currentValue: filter.current,
          suffix: filter.suffix,
        };
      });
    },
  },
  watch: {
    filters: {
      deep: true,
      handler: function(value, oldVal) {
        // console.log(value,oldVal);
        let activeFilter = value.filter((filter, index) => {
          return filter.currentValue !== oldVal[index].currentValue;
        });
        //console.log(activeFilter);
        this.setFilterVariable(activeFilter[0]);
      },
    },
  },
  methods: {
    setFilterVariable(activeFilter) {
      document.documentElement.style.setProperty(
        `--${activeFilter.name}`,
        `${activeFilter.currentValue}${activeFilter.suffix}`
      );
      //console.log(document);
    },
  },
};
</script>

<style scoped>
.display-container {
  background-color: #e0aaff;
  color: var(--colblack);
}
</style>
