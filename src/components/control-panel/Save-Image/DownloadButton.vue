<template>
  <div class="download-button flexbox flex-1  flex-justify-end">
    <button class="download-btn" @click="downloadImage">Download</button>
  </div>
</template>

<script>
export default {
  computed: {
    image() {
      return this.$store.getters.getImage;
    },
  },
  methods: {
    downloadImage() {
      //const { source, width, height, filterString } = this.image;
      const imageToDownload = new Image(
        this.image.width.substring(0, this.image.width.length),
        this.image.height.substring(0, this.image.height.length - 2)
      );
      imageToDownload.onload = () => {
        //console.log(imageToDownload.src);
        let canvas = document.createElement("canvas");
        canvas.width = this.image.width.substring(
          0,
          this.image.width.length - 2
        );
        canvas.height = this.image.height.substring(
          0,
          this.image.height.length - 2
        );
        const ctx = canvas.getContext("2d");
        ctx.filter = this.image.filterString;
        ctx.drawImage(
          imageToDownload,
          0,
          0,
          this.image.width.substring(0, this.image.width.length),
          this.image.height.substring(0, this.image.height.length - 2)
        );
        console.log(canvas);
        console.log(ctx);
        canvas.toBlob((blob) => {
          console.log(blob);
          const link = document.createElement("a");
          const url = URL.createObjectURL(blob);
          link.setAttribute("href", url);
          link.setAttribute("download", "filtered_image.png");
          link.click();
        });
      };
      imageToDownload.src = this.image.source;
    },
  },
};
</script>

<style scoped>
.download-button {
  padding: 0.5rem 1rem;
}
.download-btn {
  width: 50%;
  padding: 0.4rem 0rem;
  color: black;
  background: #8c14b1;
  border: 2px solid #240046;
  border-radius: 3px;
  font-size: 0.85rem;
  font-weight: 600;
  transition: all 0.2s ease-in;
}
.download-btn:hover {
  background: #9425b6;
  cursor: pointer;
}
.download-btn:active {
  transform: translateY(-4px);
  cursor: pointer;
}
</style>
