<template>
    <div class="nav-bar">
      <!-- Your navigation content here -->
      <div class="buttons">
        <button @click="setLightMode" class="left-button" :class="{ active: !isDarkMode }"><b>Light</b></button>
      <button @click="setDarkMode" class="right-button" :class="{ active: isDarkMode }"><b>Dark</b></button>
    </div>
    </div>
  </template>
  

<script>
export default {
  data() {
    return {
      isDarkMode: false,
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      const navBar = document.querySelector(".nav-bar");
      if (window.scrollY > 0) {
        // Add a class to change opacity when scrolling down
        navBar.classList.add("scrolled");
      } else {
        // Remove the class when at the top
        navBar.classList.remove("scrolled");
      }
    },
    setLightMode() {
      this.isDarkMode = false;
      // Apply light mode styles here
      document.documentElement.classList.remove("dark-mode");
    },
    setDarkMode() {
      this.isDarkMode = true;
      // Apply dark mode styles here
      document.documentElement.classList.add("dark-mode");
    },
  },
};
</script>

<style>
.nav-bar {
  height: 5rem;
  width: 100%;
  background-color: black;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  transition: opacity 0.2s; /* Smooth transition for opacity changes */
}

/* Add this class for scrolled state */
.nav-bar.scrolled {
  opacity: 0.9; /* Adjust the opacity value as needed */
}

/* Add dark mode styles here */
.dark-mode {
  /* Example: change background and text colors */
  background-color: #0c0b0b;
  color: white;
  /* Add more styles as needed for dark mode */
}

.buttons{
    background-color: bisque;
    width: 8rem;
    height: 1.8rem;
   margin-left: 70rem;
margin-top: 1.5rem;
display: flex;
border-radius: 14px;
}
.buttons button {
  width: 50%; /* Each button takes 50% of the width */
}
.left-button {
  border-top-left-radius: 14px;
  border-bottom-left-radius: 14px;
}

.right-button {
  border-top-right-radius: 14px;
  border-bottom-right-radius: 14px;
}
.active {
  background-color: #4287f5; /* Change the color as needed for the active button */
  color: white; /* Change the text color as needed for the active button */
}

</style>
