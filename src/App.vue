<template>
  <EmployeesList></EmployeesList>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import EmployeesList from "./components/EmployeesList.vue";

export default defineComponent({
  name: "App",
  components: { EmployeesList },
});
</script>

<style>
body {
  background-color: rgba(0, 0, 0, 0.769);
  margin: 0;
  padding: 0;
  color: white;
}

html {
  margin: 0;
  padding: 0;
  height: 100%;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
