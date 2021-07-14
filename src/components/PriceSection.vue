<template>
  <section id="price-section">
    <h1 class="section-title">Our Pricing</h1>
    <div class="switch-container">
      <span>Annually</span>
      <input type="checkbox" name="price-switch" id="price-switch" checked />
      <label for="price-switch" @click="switchPayment"></label>
      <span>Monthly</span>
    </div>
    <div class="prices-container">
      <PriceBox
        v-for="price in prices"
        :key="price"
        :price="price"
        :paidAnnually="paidAnnually"
        :class="price.isHighlight && 'highlight'"
      />
    </div>
  </section>
</template>

<script>
import PriceBox from "./PriceBox.vue";

export default {
  name: "PriceSection",
  components: { PriceBox },
  data() {
    return {
      paidAnnually: false,
      prices: [
        {
          name: "Basic",
          isHighlight: false,
          priceMonthly: "19,99",
          priceAnnually: "14,99",
          features: [
            "500 GB Storage",
            "2 Users allowed",
            "Up to 3 GB data transfer",
          ],
        },
        {
          name: "Professional",
          isHighlight: true,
          priceMonthly: "29,99",
          priceAnnually: "24,99",
          features: [
            "1 TB Storage",
            "5 Users allowed",
            "Up to 10 GB data transfer",
          ],
        },
        {
          name: "Master",
          isHighlight: false,
          priceMonthly: "39,99",
          priceAnnually: "34,99",
          features: [
            "3 TB Storage",
            "Unlimited users allowed",
            "Up to 50 GB data transfer",
          ],
        },
      ],
    };
  },
  methods: {
    switchPayment() {
      this.paidAnnually = !this.paidAnnually;
    },
  },
};
</script>

<style scoped>
#price-section {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  padding: 5rem;
  background-color: #f5f5f5;
}

.section-title {
  font-size: 3rem;
  margin-bottom: 3rem;
}

.prices-container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex: 100% 0 0;
  max-width: 70vw;
}

.switch-container {
  width: 100%;
  text-align: center;
  margin-bottom: 3rem;
}

#price-switch[type="checkbox"] {
  height: 0;
  width: 0;
  margin: 0;
  padding: 0;
  visibility: hidden;
}

#price-switch + label {
  cursor: pointer;
  text-indent: -9999px;
  width: 40px;
  height: 20px;
  border: 1px solid gray;
  display: inline-block;
  vertical-align: bottom;
  border-radius: 100px;
  position: relative;
  margin: 0 1rem;
}

#price-switch + label:after {
  content: "";
  position: absolute;
  top: 1px;
  left: 1px;
  width: 16px;
  height: 16px;
  background-color: gray;
  border-radius: 90px;
  transition: 0.3s;
}

#price-switch:checked + label:after {
  left: calc(100% - 1px);
  transform: translateX(-100%);
}

#price-switch:active:after {
  width: 130px;
}
</style>
