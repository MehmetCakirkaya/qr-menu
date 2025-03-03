<template>
  <div class="top-nav">
    <router-link to="/"
      ><img class="rounded" src="https://placehold.co/50" alt=""
    /></router-link>
    <h1 v-if="active" class="restaurant-name">Iskender Pasha</h1>
    <span>
      <span class="d-flex">
        <div class="middle">
          <!-- <span class="text">light</span> -->
          <div
            @click="toggleDarkMode($event)"
            :class="isDarkMode ? 'switch dark' : 'switch'"
          >
            <span class="sun"></span>
            <span class="moon"></span>
            <!-- sun stuff -->
            <span class="sun--bubble--left"></span>
            <span class="sun--bubble--right"></span>
            <!-- sun stuff end -->
            <!-- moon stuff -->
            <span class="moon--bubble--left"></span>
            <span class="moon--bubble--middle"></span>
            <span class="moon--bubble--right"></span>
            <span class="moon--star--left"></span>
            <span class="moon--star--right"></span>
            <!-- moon stuff end -->
          </div>
          <!-- <span class="text">dark</span> -->
        </div>
        <img
          style="max-width: 40px"
          class="rounded"
          src="assets/img/tr.png"
          alt=""
        />
      </span>
    </span>
  </div>
</template>

<script>
export default {
  name: "TopLogo",
  props: {
    active: {
      type: Boolean,
      required: true,
    },
  },
  data() {
    return {
      isDarkMode: false, // Başlangıçta light mode
    };
  },
  mounted() {
    const currentTheme = localStorage.getItem("theme");
    if (currentTheme) {
      document.documentElement.setAttribute("data-theme", currentTheme);
      this.isDarkMode = currentTheme === "dark";
    }
  },
  methods: {
    toggleDarkMode(event) {
      console.log(event);
      event.currentTarget.classList.toggle("dark");

      this.isDarkMode = !this.isDarkMode;
      const newTheme = this.isDarkMode ? "dark" : "light";
      document.documentElement.setAttribute("data-theme", newTheme);
      localStorage.setItem("theme", newTheme);
    },
  },
};
</script>

<style>
.top-nav {
  padding: 10px;
  display: flex;
  justify-content: space-between;
  backdrop-filter: blur(4px);
  position: relative;
  z-index: 9;
  align-items: center;
}

.restaurant-name {
  color: var(--title-color);
}

/* Light Dark Mode Switch */

.middle {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-right: 10px;
}
.switch {
  width: 40px;
  height: 24px;
  background: #e0e3e9;
  border-radius: 40px;
  padding: 5px;
  transition: all 125ms;
  position: relative;
  overflow: hidden;
}
.switch .moon,
.switch .sun {
  width: 14px;
  height: 14px;
  display: block;
  border-radius: 50%;
  position: relative;
  position: absolute;
  transition: all 125ms;
}
.switch .moon {
  opacity: 0;
  background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 467.9 512"><path fill="white" d="M391.17,73.24A255.55,255.55,0,0,0,182.83,1.65c-11.15,1.27-14.55,15.75-5.3,21.91,105.23,70.1,120,218,32.16,307.45A200.42,200.42,0,0,1,15.11,384.42c-10.78-2.84-19.32,9.35-12.89,18.5a257.79,257.79,0,0,0,30.39,35.82c100.88,99,262.94,97.53,362-3.47S492.17,172.33,391.17,73.24Z"/></svg>');
  background-size: 100%;
}
.switch .moon--bubble--left,
.switch .moon--bubble--right,
.switch .moon--bubble--middle {
  background: white;
  display: block;
  border-radius: 50%;
  position: absolute;
  opacity: 0;
  transition: cubic-bezier(0.65, 0.38, 0.36, 1.5) all 500ms;
  width: 2px;
  height: 2px;
}
.switch .moon--bubble--left {
  left: 5px;
  top: 13px;
  transform: translateX(50px);
}
.switch .moon--bubble--right {
  left: 13px;
  top: 9px;
  transform: translateX(20px);
}
.switch .moon--bubble--middle {
  left: 18px;
  top: 5px;
  transform: translateX(40px);
}
.switch .moon--star--left,
.switch .moon--star--right {
  background: white;
  display: block;
  border-radius: 50%;
  position: absolute;
  opacity: 0;
  transition: cubic-bezier(0.65, 0.38, 0.36, 1.5) all 500ms;
  width: 5px;
  height: 5px;
  background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" aria-hidden="true" focusable="false" data-prefix="fas" data-icon="star" class="svg-inline--fa fa-star fa-w-18" role="img" viewBox="0 0 576 512"><path fill="white" d="M259.3 17.8L194 150.2 47.9 171.5c-26.2 3.8-36.7 36.1-17.7 54.6l105.7 103-25 145.5c-4.5 26.3 23.2 46 46.4 33.7L288 439.6l130.7 68.7c23.2 12.2 50.9-7.4 46.4-33.7l-25-145.5 105.7-103c19-18.5 8.5-50.8-17.7-54.6L382 150.2 316.7 17.8c-11.7-23.6-45.6-23.9-57.4 0z"/></svg>');
  background-size: contain;
  background-repeat: no-repeat;
}
.switch .moon--star--left {
  left: 5px;
  top: 5px;
  transform: translateX(40px);
}
.switch .moon--star--right {
  left: 17px;
  top: 12px;
  transform: translateX(20px);
}
.switch .sun {
  opacity: 1;
  background-color: white;
}
.switch .sun--bubble--left,
.switch .sun--bubble--right {
  background: white;
  display: block;
  border-radius: 50%;
  position: absolute;
  opacity: 1;
  transition: cubic-bezier(0.65, 0.38, 0.36, 1.5) all 500ms;
}
.switch .sun--bubble--left {
  width: 2px;
  height: 2px;
  left: 22px;
  top: 10px;
}
.switch .sun--bubble--right {
  width: 5px;
  height: 5px;
  left: 26px;
  top: 5px;
}
.switch.dark {
  background-color: #1f2532;
}
.switch.dark .moon {
  transform: translateX(16px);
  opacity: 1;
}
.switch.dark .moon--bubble--left,
.switch.dark .moon--star--left,
.switch.dark .moon--bubble--right,
.switch.dark .moon--star--right,
.switch.dark .moon--bubble--middle,
.switch.dark .moon--star--middle {
  opacity: 1;
  transform: translateX(0px);
}
.switch.dark .sun {
  transform: translateX(16px);
  opacity: 0;
}
.switch.dark .sun--bubble--left {
  transform: translateX(-50px);
  opacity: 0;
}
.switch.dark .sun--bubble--right {
  transform: translateX(-30px);
  opacity: 0;
}
.text {
  font-family: arial;
  font-size: 12px;
  font-weight: 700;
  margin: 0 10px;
}
</style>
