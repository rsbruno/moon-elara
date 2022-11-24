<template>
  <NavBar />
</template>

<script>
import NavBar from "~/components/NavBar.vue";
export default {
  comments: {
    NavBar,
  },
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');
* {
  font-family: 'Poppins', sans-serif;
  padding: 0;
  margin: 0;
}
</style>