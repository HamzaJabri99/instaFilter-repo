<template>
  <img
    v-show="imageSource"
    :style="{ filter: filters }"
    ref="image"
    class="display-image"
    crossorigin="Anonymous"
  />
  <!-- <h4 > 📷 Please Enter a Valid image URL </h4> -->
</template>

<script>
import { mapActions } from "vuex";
export default {
  data() {
    return {
      width: 0,
      height: 0,
    };
  },
  computed: {
    imageSource() {
      return this.$store.getters.getImageSource;
    },
    filters() {
      const filters = this.$store.getters.getFilters;
      let filterString = "";
      filters.forEach((filter) => {
        //const {name, current, suffix}=filter
        filterString += `${filter.name}(${filter.current}${filter.suffix}) `;
      });
      filterString = filterString.trim();
      console.log(filterString);
      this.setFilterString_STORE(filterString);
      return filterString;
    },
  },
  watch: {
    imageSource: function(val) {
      this.$refs.image.src = this.imageSource;
      console.log(this.$refs.image.src);
      setTimeout(() => {
        this.getImageSize();
      }, 500);
    },
  },
  methods: {
    ...mapActions(["setImageSize_STORE", "setFilterString_STORE"]),
    getImageSize() {
      const image = document.querySelector(".display-image");
      const imageCompedStyles = window.getComputedStyle(image);
      console.log(imageCompedStyles.width, imageCompedStyles.height);
      const payload = {
        width: imageCompedStyles.width,
        height: imageCompedStyles.height,
      };
      this.setImageSize_STORE(payload);
    },
  },
};
</script>

<style scoped>
.display-image {
  max-width: 50%;
  max-height: 90%;
  /* filter: 
     brightness(var(--brightness))
     contrast(var(--contrast))
     grayscale(var(--grayscale))
     hue-rotate(var(--hue-rotate))
     invert(var(--invert))
     saturate(var(--saturate))
     sepia(var(--sepia))
     ; */
}
@media screen and (max-width: 600px) {
  .display-image {
    max-width: 80%;
    max-height: 50%;
  }
}
</style>
