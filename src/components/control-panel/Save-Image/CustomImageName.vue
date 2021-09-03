<template>
  <div class="custom-image-name flex-1">
    <label for="image-name-input " class="image-name-label flex-1">
      Custom Name
    </label>
    <div class="image-input">
      <input
        type="text"
        class="image-name-input"
        id="image-name-input"
        v-model="customImageName_STORE"
      />
    </div>
  </div>
</template>

<script>
export default {
  computed: {
    customImageName_STORE: {
      get() {
        return this.$store.getters.getCustomName;
      },
      set(value) {
        this.$store.commit("setCustomImageName_MUTA", value);
      },
    },
  },
};
</script>

<style scoped>
.custom-image-name {
  color: #240046;
  margin: 0.5rem 0 0 1rem;
}
.image-name-label {
  font-weight: 500;
  font-size: 150%;
  margin-bottom: 1rem;
  font-weight: bolder;
}

.image-name-input {
  font-size: 1.1rem;
  padding: 0.1rem 0.25rem;
  outline: none;
  margin: 1rem 0rem 0rem 0rem;
  border: 2px solid #212121;
  border-radius: 5px;
}
</style>
