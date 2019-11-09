<template>
  <div id="app" class="bg-blue h-screen w-screen flex justify-center items-center">
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import "./assets/tailwind.css";
export default {
  name: "app",
  components: {
    HelloWorld
  }
};
</script>
