<template>
  <section class="merchant-list">
    <h2>Estabelecimentos Disponíveis</h2>
    <aside class="list-cards">
      <MerchantCardApresentation
        v-for="merchant in merchants"
        :key="merchant"
        :merchant="merchant"
      />
    </aside>
    <ButtonLink />
  </section>
</template>

<script lang="ts">
import ButtonLink from "./ButtonLink.vue";
import MerchantCardApresentation, {
  IMerchant,
} from "./MerchantCardApresentation.vue";
export default {
  components: { MerchantCardApresentation, ButtonLink },
  data() {
    return {
      merchants: [
        {
          name: "Padaria Avenida",
          logo: "data:image/png;base64,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",
          category: "Sorveteria",
          distance: 1.2,
          timeDelivery: "60-90",
          deliveryPrice: 0,
          avaliation: 4.5,
        },
        {
          name: "Von's Burger Bar",
          logo: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRfbX2fWgIz-nqmiajYZPDeHP5lbI_83e7Kqg&usqp=CAU",
          category: "Hamburgueria",
          distance: 4.8,
          timeDelivery: "30-90",
          deliveryPrice: 3,
          avaliation: 3,
        },
        {
          name: "Dom Gourmet Atesanal",
          logo: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRQFgudauRFrMOQuVtgSAaYtKe0JMfrR3gxZw&usqp=CAU",
          category: "Hamburgueria",
          distance: 3.7,
          timeDelivery: "30-90",
          deliveryPrice: 6,
          avaliation: 4,
        },
        {
          name: "Churrascaria Barbecue",
          logo: "data:image/jpeg;base64,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",
          category: "Churrascaria",
          distance: 4.8,
          timeDelivery: "60",
          deliveryPrice: 10,
          avaliation: 5,
        },
        {
          name: "Sorveteria & Açaí Central",
          logo: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQzEnxoFKJakbMV2gFHHZCZUKSMCWFdLIKY-g&usqp=CAU",
          category: "Sorveteria",
          distance: 9,
          timeDelivery: "90-100",
          deliveryPrice: 5,
          avaliation: 4.5,
        },
        {
          name: "Bolt Açaí",
          logo: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRKNhtLyiKJ1UJmIjA7yQvR2zigTaMl_TnQcQ&usqp=CAU",
          category: "Açaí",
          distance: 0.5,
          timeDelivery: "30",
          deliveryPrice: 0,
          avaliation: 4.5,
        },
        {
          name: "Karma Sushi",
          logo: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRdkG2x9_v06hdaULqRPVuY9tl9gzxqc83R6g&usqp=CAU",
          category: "Sushi Bar",
          distance: 6.5,
          timeDelivery: "60-80",
          deliveryPrice: 10,
          avaliation: 4,
        },
      ] as IMerchant[],
    };
  },
};
</script>

<style lang="scss" scoped>
.merchant-list {
  margin-top: 12px;
  h2 {
    border-bottom: solid 1px #00a296;
    font-size: 1rem;
    padding-bottom: 4px;
    color: #7b1fa2;
  }
  .list-cards {
    justify-content: flex-start;
    align-items: flex-start;
    margin-bottom: 12px;
    margin-top: 12px;
    flex-wrap: wrap;
    display: flex;
    gap: 8px;
  }
}
</style>