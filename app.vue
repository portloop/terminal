<template>
  <div>
    <NuxtPage />
  </div>
</template>


<style scoped>
  html, body {
    height: 100vh;
    background: #fffefa
  }

  div {
    background-color: #fffefa
  }


  @font-face {
    font-family: 'Recoletta-Regular';
    src: url(./assets/Recoleta-Regular.ttf);
  }

  .slide-fade-enter-active, .slide-fade-leave-active {
    transition: opacity 0.5s, transform 0.5s;
  }
  .slide-fade-enter-from, .slide-fade-leave-to {
    opacity: 0;
    transform: translateY(100px);
  }
  .slide-fade-enter-to, .slide-fade-leave-from {
    opacity: 1;
    transform: translateY(0);
  }
</style>