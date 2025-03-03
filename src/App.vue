<template>
  <!-- <TopLogo /> -->
  <RouterView />
  <div class="basket-btn">
    <span class="basket-inside">
      <router-link to="/basket">
        <lord-icon
          src="https://cdn.lordicon.com/jprtoagx.json"
          trigger="hover"
          stroke="bold"
          colors="primary:#121331,secondary:#121331"
          style="width: 50px; height: 50px"
        >
        </lord-icon>
      </router-link>
    </span>
  </div>
</template>

<script>
// import TopLogo from "./components/TopLogo.vue";

export default {
  name: "App",
  components: {
    // TopLogo,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}
.basket-btn {
  padding: 20px;
  border-radius: 50%;
  width: 70px;
  height: 70px;
  background-color: #b1c29e75;
  position: fixed;
  bottom: 10px;
  right: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.basket-inside {
  background-color: #b1c29e;
  border-radius: 50%;
  padding: 10px;
  width: 60px;
  height: 60px;
  display: flex;
  justify-content: center;
  align-items: center;
  border: 1px solid gray;
}
</style>
