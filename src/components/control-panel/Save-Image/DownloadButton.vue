<template>
  <div class="download-button flexbox flex-1  flex-justify-end">
    <button class="download-btn">Download</button>
  </div>
</template>

<script>
export default {};
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
  transform: translateY(-5px);
  cursor: pointer;
}
</style>
