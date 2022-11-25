<template>
  <div class="filter-tag-container">
    <h6>{{ nameTag }}</h6>
  </div>
</template>

<script>
export default {
  props: ["nameTag"],
};
</script>

<style lang="scss">
.filter-tag-container {
  width: min-content;
  border: solid 2px #ddd;
  white-space: nowrap;
  padding: 5px 10px;
  border-radius: 50px;
  transition: all ease 400ms;
  cursor: pointer;

  &:hover {
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.12);
    transform: scaleX(1.05);
  }

  h6 {
    font-weight: 500;
    font-size: 0.75rem;
    color: #717171;
    text-transform: capitalize;
  }
}
</style>