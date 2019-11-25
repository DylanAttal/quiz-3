<template>
  <div class="winner-modal">
    <h1>Congratulations!</h1>
  </div>
</template>

<script>
export default {
  name: 'Winner'
}
</script>

<style>
.winner-modal {
  background-color: #eee;
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 10;
  height: 350px;
  width: 550px;
}
</style>
