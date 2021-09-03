<template>
  <div class="save-image-panel flex-1">
    <CustomImageName />
  </div>
</template>

<script>
import CustomImageName from "./CustomImageName";
export default {
  components: {
    CustomImageName,
  },
};
</script>

<style scoped>
.save-image-panel {
  min-height: 7rem;
  border-top: 3px solid black;
}
</style>
