<template>
  <div class="container">
    <nav>
      <ul>
        <li class="col-12 col-md-3 text-center"><h1>Restaurant</h1></li>
        <li class="col-12 col-md-8 d-flex justify-content-around">
          <input
            type="search"
            name="search"
            id="search"
            placeholder="Search Food.."
          />
        </li>
      </ul>
    </nav>

    <section class="categories">
      <div>
        <Categories />
      </div>
    </section>
  </div>
</template>

<script>
import Categories from "@/components/Categories.vue";

export default {
  name: "HomePage",
  components: {
    Categories,
  },
  data() {
    return {
      msg: "Hello World!",
    };
  },
  methods: {},
};
</script>
