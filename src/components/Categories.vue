<template>
  <router-link to="/products" id="sarooh" style="padding: 10px 5px" class="col-12 col-md-4">
    <div
      style="background-color: #7c444f; justify-content: end"
      class="category-box"
    >
      <div class="col-8">
        <img
          style="bottom: 10px; left: -125px; width: 230px"
          src="/assets/img/sarooh.png"
          alt="Sarooh"
        />
        <h1><b>Sarooh</b></h1>
        <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit.</p>
      </div>
    </div>
  </router-link>
  <router-link to="/products" id="shawarma" style="padding: 10px 5px" class="col-12 col-md-4">
    <div
      style="background-color: #b1c29e; justify-content: start"
      class="category-box"
    >
      <div class="col-8">
        <img
          style="bottom: -30px; right: -60px; width: 250px"
          src="/assets/img/shawarma.png"
          alt="shawarma"
        />
        <h1><b>Shawarma</b></h1>
        <p>Lorem ipsum dolor sit amet consectetur, deleniti amet!</p>
      </div>
    </div>
  </router-link>
  <router-link to="/products" id="burgers" style="padding: 10px 5px" class="col-12 col-md-4">
    <div
      style="background-color: #e16a54; justify-content: end"
      class="category-box"
    >
      <div class="col-8">
        <img
          style="top: 10px; left: -100px; width: 220px"
          src="/assets/img/burger.png"
          alt="Burger"
        />
        <img
          style="
            bottom: -40px;
            right: -20px;
            width: 120px;
            transform: rotate(-30deg);
          "
          src="/assets/img/french-fries.png"
          alt="french fries"
        />
        <h1><b>Burgers</b></h1>
        <p>Lorem ipsum dolor sit deleniti amet!</p>
      </div>
    </div>
  </router-link>
  <router-link to="/products" id="grill" style="padding: 10px 5px" class="col-12 col-md-4">
    <div
      style="background-color: #f39e60; justify-content: start"
      class="category-box"
    >
      <div class="col-8">
        <img
          style="
            bottom: -75px;
            right: -60px;
            width: 200px;
            transform: rotate(-30deg);
          "
          src="/assets/img/grill.png"
          alt="grill"
        />
        <h1><b>Grill Plate</b></h1>
        <p>Lorem ipsum dolor sit amet deleniti amet!</p>
      </div>
    </div>
  </router-link>
  <router-link to="/products" id="salads" style="padding: 10px 5px" class="col-12 col-md-4">
    <div
      style="background-color: #7c444f; justify-content: end"
      class="category-box"
    >
      <div class="col-8">
        <img
          style="bottom: 0px; left: -35px; width: 200px"
          src="/assets/img/salad2.png"
          alt="Salads"
        />
        <h1><b>Salads</b></h1>
        <p>Lorem ipsum dolor sit amet consectetur, deleniti amet!</p>
      </div>
    </div>
  </router-link>
  <router-link to="/products" id="appetizers" style="padding: 10px 5px" class="col-12 col-md-4">
    <div
      style="background-color: #b1c29e; justify-content: start"
      class="category-box"
    >
      <div class="col-8">
        <img
          style="top: 27px; right: -30px; width: 115px"
          src="/assets/img/meze.png"
          alt="Appetizers"
        />
        <img
          style="bottom: -55px; right: 0px; width: 150px"
          src="/assets/img/meze2.png"
          alt="Appetizers"
        />
        <h1><b>Appetizers</b></h1>
        <p>Lorem ipsum dolor sit deleniti amet!</p>
      </div>
    </div>
  </router-link>
  <router-link to="/products" id="pizzas" style="padding: 10px 5px" class="col-12 col-md-4">
    <div
      style="background-color: #e16a54; justify-content: end"
      class="category-box"
    >
      <div class="col-8">
        <img
          style="bottom: -75px; left: -60px; width: 180px"
          src="/assets/img/pizza.png"
          alt="Pizza"
        />
        <h1><b>Pizzas</b></h1>
        <p>Lorem ipsum dolor sit amet deleniti amet!</p>
      </div>
    </div>
  </router-link>
  <router-link to="/products" id="owen" style="padding: 10px 5px" class="col-12 col-md-4">
    <div
      style="background-color: #f39e60; justify-content: start"
      class="category-box"
    >
      <div class="col-8">
        <img
          style="
            top: -70px;
            right: -90px;
            width: 300px;
            transform: rotate(-10deg);
          "
          src="/assets/img/pide.png"
          alt="Owen Fatira"
        />
        <img
          style="bottom: -70px; right: 10px; width: 130px"
          src="/assets/img/lahmacun.png"
          alt="Owen Fatira"
        />
        <h1><b>Owen Fatira</b></h1>
        <p>Lorem ipsum dolor sit deleniti amet!</p>
      </div>
    </div>
  </router-link>
  <router-link to="/products" id="drinks" style="padding: 10px 5px" class="col-12 col-md-4">
    <div
      style="background-color: #7c444f; justify-content: end"
      class="category-box"
    >
      <div class="col-8">
        <img
          style="
            bottom: -10px;
            left: -10px;
            width: 117px;
            transform: rotate(20deg);
          "
          src="/assets/img/juice2.png"
          alt="Drinks"
        />
        <h1><b>Drinks</b></h1>
        <p>Lorem ipsum dolor sit amet deleniti amet!</p>
      </div>
    </div>
  </router-link>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      msg: "Hello World!",
    };
  },
};
</script>

<style>
body {
  padding: 0;
  margin: 0;
}

nav ul {
  list-style: none;
  padding: 8px;
  width: 100%;
  display: flex;
  flex-wrap: wrap;
}

nav ul li {
  padding: 5px;
}

nav ul li input {
  padding: 8px;
  border-radius: 20px;
  width: 100%;
  outline: 0;
  border: 1px solid rgb(184, 184, 184);
  padding-left: 15px;
}

.categories {
  flex-wrap: wrap;
  display: flex;
  flex-direction: row;
  padding: 5px 10px;
}

.category-box {
  overflow: hidden;
  position: relative;
  color: white;
  min-height: 200px;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  /* margin-bottom: 20px; */
  border-radius: 15px;
  padding: 20px 30px;
  transition: all 1s;
}

.category-box img {
  position: absolute;
}

.overlay {
  position: fixed;
  top: 0;
  left: 0;
  height: 100vh;
  z-index: 1000;
  transition: all 1s ease;
}
a {
  text-decoration: none;
}
</style>
