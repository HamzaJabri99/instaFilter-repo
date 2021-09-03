<template>
  <div class="save-image-panel flex-1">
    <CustomImageName />
    <DownloadButton />
  </div>
</template>

<script>
import CustomImageName from "./CustomImageName";
import DownloadButton from "./DownloadButton.vue";
export default {
  components: {
    CustomImageName,
    DownloadButton,
  },
};
</script>

<style scoped>
.save-image-panel {
  height: 100%;
  border-top: 3px solid black;
}
</style>
