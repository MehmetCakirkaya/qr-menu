<template>
  <div v-if="isVisible" class="modal">
    <div class="modal-content">
      <span class="close" @click="closeModal">&times;</span>
      <img src="https://placehold.co/300" alt="Ürün Resmi" />

      <h2>{{ item.title }}</h2>
      <p>{{ item.description }}</p>
      <p>Fiyat: {{ item.price }}</p>

      <div class="quantity-section">
        <div class="quantity-controls">
          <button @click="decreaseQuantity">-</button>
          <span>{{ quantity }}</span>
          <button @click="increaseQuantity">+</button>
        </div>
        <button class="add-to-cart">Sepete Ekle</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      quantity: 1,
    };
  },
  props: {
    isVisible: {
      type: Boolean,
      required: true,
    },
    item: {
      type: Object,
      required: true,
    },
  },
  methods: {
    closeModal() {
      this.$emit("close");
    },
    increaseQuantity() {
      this.quantity += 1;
    },
    decreaseQuantity() {
      if (this.quantity > 1) {
        this.quantity -= 1;
      }
    },
  },
};
</script>

<style scoped>
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
}

.modal-content {
  background-color: var(--base-bg-color);
  color: var(--title-color);
  width: 35%;
  padding: 20px;
  border-radius: 8px;
  position: relative;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  text-align: left;
}

@media (max-width: 768px) {
  .modal-content {
    width: 80%;
  }
}

.close {
  position: absolute;
  top: 10px;
  right: 10px;
  font-size: 24px;
  font-weight: bold;
  cursor: pointer;
  width: 30px;
  height: 30px;
  background: rgb(225 40 40);
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 8px;
  color: white;
}

.modal-content img {
  width: 100%;
  height: auto;
  max-width: 300px;
  margin: auto;
  margin-bottom: 20px;
}

.quantity-section {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 20px;
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
.add-to-cart {
  background-color: var(--btn);
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 4px;
  cursor: pointer;
}

.add-to-cart:hover,
.quantity-controls button:hover {
  opacity: 0.8;
}
</style>
