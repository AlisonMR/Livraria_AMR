<script setup>
import HeaderComp from "@/components/Template/HeaderComp.vue";
</script>

<template>
  <header-comp />
  <main>
    <RouterView />
  </main>
</template>

<style>
body {
  background: linear-gradient(180deg, rgb(97, 24, 139) 37%, rgb(47, 14, 85) 53%, rgba(0, 0, 0, 0.918) );
}
#app {
  max-width: 1280px;
  margin: 0 auto;
  font-weight: normal;
  height: 100vh;
}
main {
  height: 80%;
}
a {
  color: inherit;
  text-decoration: none;
}
.router-link-active {
  color: #9733f5;
  font-style: italic;
}
</style>
