<template>
  <section>
    <TopLogo :active="activeNme" />
    <Modal
      :isVisible="showModal"
      :item="selectedItem"
      @close="showModal = false"
    />

    <div class="product-list">
      <div class="products-top">
        <div class="category-name">
          <h1>{{ categoryName }}</h1>
        </div>
      </div>
      <div class="product-body">
        <div class="container mt-2 p-3">
          <div class="row">
            <div
              @click="openModal(item)"
              class="col-6 col-md-2 mb-2 p-2"
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
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import TopLogo from "@/components/TopLogo.vue";
import Modal from "@/components/ProductModal.vue";

export default {
  name: "CategoryProducts",
  data() {
    return {
      activeNme: false,
      isModalOpen: false,
      showModal: false,
      selectedItem: null,

      categoryName: "Category Name",
      products: [
        {
          id: 1,
          title: "Ürün 1",
          description:
            "BLorem ipsum dolor sit amet consectetur, adipisicing elit. Consequatur doloremque error et hic odio excepturi enim eum corporis asperiores sunt.",
          price: 99.99,
        },
        {
          id: 2,
          title: "Ürün 2",
          description:
            "sit amet consectetur, adipisicing elit. Consequatur doloremque error et hic",
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
  components: {
    TopLogo,
    Modal,
  },
  methods: {
    openModal(item) {
      this.selectedItem = item;
      this.showModal = true;
    },
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
  height: 300px;
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
.card-body {
  padding: 10px;
}
.card-title,
.card-text {
  white-space: normal;
  overflow-wrap: break-word;
}
.card-text {
  display: -webkit-box;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
  -webkit-line-clamp: 2;
  line-clamp: 2;
  min-height: 48px;
  max-height: 48px;
}

/* Modal Stilleri */
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5); /* Yarı saydam arka plan */
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
}

.modal-content {
  background-color: white;
  width: 90%; /* %90 genişlik */
  padding: 20px;
  border-radius: 8px;
  position: relative;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}
.close {
  position: absolute;
  top: 10px;
  right: 10px;
  font-size: 24px;
  font-weight: bold;
  cursor: pointer;
}

.open-modal-button {
  padding: 10px 20px;
  background-color: #007bff;
  color: white;
  text-align: center;
  border-radius: 5px;
  cursor: pointer;
  margin: 20px;
  display: inline-block;
}

/* Ekranın küçük olduğu durumlar için mobil uyumlu hale getirir */
@media (max-width: 600px) {
  .modal-content {
    width: 95%; /* Küçük ekranlarda genişliği artır */
  }
}
</style>
