<template>
  <section class="list-tags">
    <FilterTag v-for="tag in tags" :key="tag" :nameTag="tag" />
  </section>
</template>

<script>
import FilterTag from "./FilterTag.vue";

export default {
  components: { FilterTag },
  data() {
    return {
      tags: [
        "Promoçoes",
        "aceita cupom",
        "entrega grátis",
        "para retirar",
        "Vale-refeição",
        "Restaurantes em Destaque",
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.list-tags {
  display: flex;
  gap: 8px;
}
</style>