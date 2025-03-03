<template>
  <TopLogo :active="activeNme" />
  <div class="container">
    <div class="basket-body">
      <div class="col-12 col-md-8">
        <div class="container">
          <div
            v-for="item in products"
            :key="item.id"
            class="basket-box col-12 rounded"
          >
            <div class="basket-details">
              <img
                src="../../public/assets/img/products/pizza.jpg"
                alt="Ürün Resmi"
                class="product-image"
              />
              <div class="d-flex flex-wrap flex-column">
                <h2>{{ item.title }}</h2>
                <p>{{ item.price }} TL</p>
              </div>
            </div>
            <div class="basket-interaction">
              <div class="quantity-controls">
                <button @click="decreaseQuantity(item)">-</button>
                <span>{{ item.amount }}</span>
                <button @click="increaseQuantity(item)">+</button>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="col-12 col-md-4">
        <div class="col-12 text-start basket-result">
          <p>Toplam Ücret: 297.90</p>
          <button class="btn btn-lg p-2">Garson Çağır</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import TopLogo from "@/components/TopLogo.vue";

export default {
  name: "ShopBasket",
  components: {
    TopLogo,
  },
  data() {
    return {
      activeNme: false,

      products: [
        {
          id: 1,
          title: "Ürün 1",
          description:
            "BLorem ipsum dolor sit amet consectetur, adipisicing elit. Consequatur doloremque error et hic odio excepturi enim eum corporis asperiores sunt.",
          price: 99.99,
          amount: 2,
        },
        {
          id: 2,
          title: "Ürün 2",
          description:
            "sit amet consectetur, adipisicing elit. Consequatur doloremque error et hic",
          price: 79.99,
          amount: 3,
        },
        {
          id: 3,
          title: "Ürün 3",
          description: "Bu ürün açıklaması 3.",
          price: 59.99,
          amount: 3,
        },
      ],
    };
  },
  methods: {
    increaseQuantity(item) {
      item.amount += 1;
    },
    decreaseQuantity(item) {
      if (item.amount > 1) {
        item.amount -= 1;
      }
    },
  },
};
</script>

<style>
.basket-body {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  margin-top: 20px;
}
.basket-body img {
  max-width: 100px;
  min-width: 100px;
}
.basket-box {
  display: flex;
  align-items: center;
  padding: 10px;
  margin-bottom: 10px;
  background-color: var(--basket-box);
}

.basket-result {
  padding: 20px;
  border-left: 2px solid gray;
  color: var(--title-color);
}

.basket-result button {
  background-color: var(--btn);
  border-radius: 12px;
  color: white;
}

.product-image {
  width: 70px;
  height: 70px;
  margin-right: 20px;
}

.basket-details {
  flex-grow: 1;
  display: flex;
  flex-wrap: nowrap;
  align-items: center;
}

.basket-details h2,
.basket-details p {
  margin: 0;
  color: var(--title-color);
}

.basket-interaction {
  text-align: right;
}

.quantity-controls {
  display: inline-flex;
  align-items: center;
  color: var(--title-color);
}

.quantity-controls button {
  background-color: var(--btn);
  color: white;
  border: none;
  padding: 5px;
  margin: 0 5px;
  cursor: pointer;
  border-radius: 4px;
  width: 30px;
  height: 30px;
}

.quantity-controls span {
  margin: 0 10px;
}

@media (max-width: 768px) {
  .basket-result {
    border: none;
  }
  .basket-body img {
    max-width: 70px;
    min-width: 70px;
  }
}
</style>
