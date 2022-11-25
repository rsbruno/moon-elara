<template>
  <div class="container-main">
    <NavBar />
    <main class="container-content">
      <ListFilterTags />

      <MerchantList />
    </main>
  </div>
</template>

<script>
import ListFilterTags from "~/components/ListFilterTags.vue";
import MerchantList from "~/components/MerchantList.vue";
import NavBar from "~/components/NavBar.vue";
export default {
  components: { NavBar, ListFilterTags, MerchantList },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Poppins&display=swap");
* {
  font-family: "Poppins", sans-serif;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.container-main {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  .container-content {
    max-width: 1366px;
    width: 100%;
  }
}
</style>