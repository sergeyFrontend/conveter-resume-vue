<template>
  <div class="avatar">
    <img :src="$attrs.value">
  </div>
</template>

<style scoped>


  .avatar img {
    width: 150px;
    height: auto;
    border-radius: 50%;
  }
</style>