<template>
  <button class="container-button">
    <h6>Ver mais</h6>
  </button>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.container-button {
  background: transparent;
  width: 100%;
  height: 40px;
  cursor: pointer;
  border: none;
  outline: none;
  transition: all ease-in-out 400ms;
  border-radius: 6px;

  &:hover {
    background: #7b1fa2;
    h6 {
      color: #fff;
    }
  }

  h6 {
    font-size: 0.8rem;
    color: #7b1fa2;
  }
}
</style>