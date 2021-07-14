<template>
  <div class="price-box">
    <div class="price-title">
      {{ price.name }}
    </div>
    <div class="price">
      {{ paidAnnually ? price.priceAnnually : price.priceMonthly }}
    </div>
    <ul class="feature-list">
      <li v-for="feature in price.features" :key="feature" class="feature">
        {{ feature }}
      </li>
    </ul>
    <a href="#" class="btn">
      Learn more
    </a>
  </div>
</template>

<script>
export default {
  name: "PriceBox",
  props: ["price", "paidAnnually"],
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.price-box {
  flex-basis: calc(100% / 3);
  padding: 3rem;
  background-color: white;
  border-radius: 10px;
  font-weight: bold;
  color: gray;
  text-align: center;
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.15);
}

.price-box:first-of-type {
  border-top-right-radius: 0;
  border-bottom-right-radius: 0;
}

.price-box:last-of-type {
  border-top-left-radius: 0;
  border-bottom-left-radius: 0;
}

.price-box.highlight {
  background: linear-gradient(180deg, lightblue, blue);
  color: white;
  padding: 5rem 3rem;
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
  z-index: 10;
}

.price-title,
.price {
  margin-bottom: 1.5rem;
}

.price {
  font-size: 3rem;
  color: #202020;
}

.highlight .price {
  color: white;
}

.feature-list {
  list-style: none;
  padding: 0;
  margin-bottom: 3rem;
}

.feature-list .feature {
  padding: 1rem 0;
  border-bottom: 1px solid lightgray;
}

.feature-list .feature:first-of-type {
  border-top: 1px solid lightgray;
}

.highlight .feature-list .feature {
  border-color: white;
}

.btn {
  display: block;
  background: linear-gradient(135deg, lightblue, blue);
  padding: 1rem;
  border-radius: 5px;
  color: white;
  text-decoration: none;
  font-weight: bold;
}

.highlight .btn {
  background: white;
  color: gray;
}
</style>
