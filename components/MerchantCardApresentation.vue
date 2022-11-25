<template>
  <section class="merchant-container">
    <div class="merchant-logo">
      <img :src="merchant.logo" :alt="merchant.name" v-if="merchant.logo" />
      <img src="../assets/images/defaultLogo.png" alt="default logo" v-else />
    </div>
    <div class="merchant-specs">
      <h4 class="merchant-name">{{ merchant.name }}</h4>
      <div class="merchant-category">
        <span class="icon-star">
          <font-awesome-icon :icon="['fa-solid', 'star']" />
        </span>
        <h5 class="text-avaliation">{{ merchant.avaliation.toFixed(1) }}</h5>
        <span class="merchant-separator"> • </span>
        <h5 class="text-category">{{ merchant.category }}</h5>
        <span class="merchant-separator"> • </span>
        <h5 class="text-distance">{{ merchant.distance }}km</h5>
      </div>
      <div class="merchant-definitions">
        <h6 class="delivery-time">{{ merchant.timeDelivery }}min</h6>
        <span class="merchant-separator"> • </span>
        <h6 class="delivery-price" v-if="merchant.deliveryPrice">
          R${{ merchant.deliveryPrice.toFixed(2) }}
        </h6>
        <h6 class="delivery-price" v-else>Grátis</h6>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { PropType } from "vue";
export interface IMerchant {
  name: string;
  logo: string | undefined;
  category: string;
  distance: number;
  timeDelivery: string;
  deliveryPrice: number;
  avaliation: number;
}

export default {
  props: {
    merchant: { type: Object as PropType<IMerchant>, required: true },
  },
};
</script>

<style lang="scss" scoped>
.merchant-container {
  transition: all ease-in-out 400ms;
  justify-content: flex-start;
  align-items: center;
  border-radius: 6px;
  padding: 4px 8px;
  display: flex;
  width: 100%;
  max-width: calc(25% - 8px);
  cursor: pointer;

  &:hover {
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.12);
  }

  .merchant-logo {
    height: 90px;
    width: 90px;
    border: solid 1px #7b1fa2;
    margin-right: 8px;
    overflow: hidden;
    border-radius: 6px;
    img {
      width: 100%;
      height: 100%;
    }
  }

  .merchant-specs {
    .merchant-name {
      font-size: 0.82rem;
    }

    .merchant-category {
      align-items: center;
      height: 1.2rem;
      display: flex;

      .icon-star {
        color: #fcbb00;
        margin-right: 3px;
        font-size: 0.7rem;
      }

      .text-avaliation,
      .text-category,
      .text-distance {
        color: #717171;
        font-size: 0.8rem;
        font-weight: 400;
      }

      .text-avaliation {
        color: #fcbb00;
      }
    }
  }

  .merchant-definitions {
    justify-content: flex-start;
    align-items: center;
    display: flex;
    height: 1.5rem;

    .delivery-time,
    .delivery-price {
      color: #717171;
      font-size: 0.8rem;
      font-weight: 400;
    }

    .delivery-price {
      color: #50a773;
    }
  }
}

.merchant-separator {
  margin: 0 4px;
  color: #717171;
}
</style>