<template>
  <TopLogo :active="activeNme" />
  <div class="container">
    <nav>
      <ul>
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
        <Categories />
    </section>
  </div>
</template>

<script>
import Categories from "@/components/Categories.vue";
import TopLogo from "@/components/TopLogo.vue";

export default {
  name: "HomePage",
  components: {
    Categories,
    TopLogo,
  },
  data() {
    return {
      activeNme: true,
    };
  },
  methods: {},
};
</script>
