<template>
  <section>
    <div class="product-list">
      <div class="products-top">
        <div class="category-name">
          <h1>{{ categoryName }}</h1>
        </div>
      </div>
      <div class="product-body">
        <div class="container mt-5 p-3">
          <div class="row">
            <!-- Ürün Kartı Başlangıcı -->
            <div
              class="col-6 col-md-2 mb-4 p-2"
              v-for="item in products"
              :key="item"
            >
              <div class="card h-100 text-start">
                <img
                  src="https://placehold.co/150"
                  class="card-img-top"
                  alt="Ürün Fotoğrafı"
                />
                <div class="card-body">
                  <h5 class="card-title">{{ item.title }}</h5>
                  <p class="card-text">
                    {{ item.description }}
                  </p>
                  <p class="card-text">
                    <strong>{{ item.price }}</strong>
                  </p>
                </div>
              </div>
            </div>
            <!-- Ürün Kartı Bitişi -->
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
// import ProductList from '@/components/ProductList.vue';

export default {
  name: "CategoryProducts",
  components: {
    // ProductList,
  },
  data() {
    return {
      msg: "Hello World!",
      categoryName: "Category Name",
      products: [
        {
          id: 1,
          title: "Ürün 1",
          description: "Bu ürün açıklaması 1.",
          price: 99.99,
        },
        {
          id: 2,
          title: "Ürün 2",
          description: "Bu ürün açıklaması 2.",
          price: 79.99,
        },
        {
          id: 3,
          title: "Ürün 3",
          description: "Bu ürün açıklaması 3.",
          price: 59.99,
        },
        {
          id: 4,
          title: "Ürün 4",
          description: "Bu ürün açıklaması 4.",
          price: 89.99,
        },
        {
          id: 5,
          title: "Ürün 5",
          description: "Bu ürün açıklaması 5.",
          price: 49.99,
        },
        {
          id: 6,
          title: "Ürün 6",
          description: "Bu ürün açıklaması 6.",
          price: 69.99,
        },
      ],
    };
  },
};
</script>

<style>
.product-list {
  color: white;
  position: absolute;
  width: 100%;
  top: 0;
  text-align: center;
}
.products-top {
  width: 100%;
  height: 250px;
  background-image: url("../../public/assets/img/shawarma2.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  display: flex;
  justify-content: center;
  align-items: center;
}
.category-name {
  padding: 20px 40px;
  backdrop-filter: blur(4px);
  border-radius: 10px;
  box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
}
.card {
  line-height: 1.5;
  font-size: 1rem;
  white-space: normal;
}

.card-title,
.card-text {
  white-space: normal;
  overflow-wrap: break-word;
}
</style>
