<template>
<div class="loaders">
    <div class="loader"></div>
</div>
</template>

<script setup>

</script>

<style lang="scss" scoped>
.loaders {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background: #000;
}
.loader {
  position: relative;
  width: 150px;
  height: 150px;
  border-radius: 50%;
  background: linear-gradient(45deg, transparent, transparent 30%, #e5f403);
  animation: loader 2s linear infinite;
}
@keyframes loader {
  0% {
    transform: rotate(0deg);
    filter: hue-rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
    filter: hue-rotate(360deg); 
  }
}
.loader:before {
  content: '';
  position: absolute;
  top: 6px;
  left: 6px;
  bottom: 6px;
  right: 6px;
  background: #000;
  border-radius: 50%;
  z-index: 1000;
}
.loader:after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  background: linear-gradient(45deg, transparent, transparent 30%, #e5f403);
  border-radius: 50%;
  z-index: 1000;
  z-index: 1;
  filter: blur(30px);
}
</style>