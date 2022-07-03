<template>
  <SignupForm />
</template>

<script>
import SignupForm from "./components/SignupForm.vue";
import "./assets/tailwind.css";

export default {
  name: "App",
  components: { SignupForm },
};
</script>

<style>
#app {
}

body {
  margin: 0;
  background: #bdabd9;
}
</style>
