<template>
  <div class="main-container">
    <div class="project-container">
      <div class="navigation">
        <button @click="prevProject" :disabled="currentIndex === 0" class="nav-button left-button" v-show="currentIndex !== 0" >
          <img src="../assets/lefticon.png" alt="Previous">
        </button>
      </div>
      <a
        v-for="(project, index) in projectData.projectsArray.slice(
          currentIndex,
          currentIndex + 3
        )"
        :key="index" :href="project.link" target="_blank" 
      >
        <div class="project-class">
          <h2>{{ project.title }}</h2>
          <div class="image-container">
            <img
              :src="project.image"
              alt=""
              class="project-image"
            >
          </div>
          <div class="project-content">
            <h3><div class="topic"><u>Topics covered:</u> {{ project.About }}</div></h3>
            <p class="project-description">{{ project.description }}</p>
            <a :href="project.link" target="_blank"><h4>{{ project.link }}</h4></a>
          </div>
        </div>
      </a>
      <div class="navigation">
        <button @click="nextProject" :disabled="currentIndex + 3 >= projectData.projectsArray.length" class="nav-button right-button" v-show="currentIndex + 3 < projectData.projectsArray.length">
          <img src="../assets/righticon.png" alt="Next">
        </button>
      </div>
    </div>
  </div>
</template>


<script>
import jsonData from "/project.json";

export default {
  data() {
    return {
      projectData: jsonData,
      currentIndex: 0,
    };
  },
  methods: {
    nextProject() {
      if (this.currentIndex + 3 < this.projectData.projectsArray.length) {
        this.currentIndex += 1;
      }
    },
    prevProject() {
      if (this.currentIndex > 0) {
        this.currentIndex -= 1;
      }
    },
    autoSlide() {
      // Function to automatically move to the next set of projects
      setInterval(() => {
        this.nextProject();
      }, 3000); // 3000 milliseconds = 3 seconds
    },
  },
 
  mounted() {
    // Start the automatic sliding when the component is mounted
    this.autoSlide();
  },
};
</script>

<style>
.main-container {
  display: flex;
  flex-direction: column; /* Display navigation buttons below projects */
  align-items: center; /* Center-align the projects */
  /* padding: 10px; */
}

.project-container {
  position: relative;
  display: flex;
  flex-direction: row; /* Display projects in a single row */
  flex-wrap: nowrap; /* Prevent wrapping to the next row */
  overflow-x: auto; /* Add horizontal scroll for smaller screens */
  justify-content: flex-start; /* Start projects at the left-most position */
  gap: 10px; /* Add spacing between projects */
  margin-bottom: 10px;
  transition: transform 0.5s;
  padding: 2rem;
  text-align: center;
}

.project-class {
  border-radius: 25px;
  box-shadow: rgba(0, 0, 0, 0.5) 0px 3px 16px;
  padding: 20px; /* Add padding to the projects for spacing */
  max-width: 370px; /* Limit the width of each project if needed */
  height: 350px; /* Set a fixed height for each card (adjust as needed) */
  overflow: hidden; /* Hide any overflowing content */
 
  margin-left: 0;
  
}

.navigation {
  display: flex;
  justify-content: space-between;
  margin-top: 8px;
  border-radius: 4px;
  position: relative;
 
}

.nav-button {
  width: 90px;
  height: 100px; /* Adjust button width as needed */
  padding: 10px 10px;
  background-color: transparent; /* Make buttons transparent by default */
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  position: absolute; /* Absolute positioning */
  top: 50%; /* Position vertically in the middle of the container */
  transform: translateY(-50%); /* Center vertically */
  opacity: 0; /* Hide buttons by default */
  transition: opacity 0.3s ease; /* Add a smooth transition effect */
}
.navigation:hover .nav-button {
  opacity: 1; /* Show buttons on hover */
}

.navigation button:disabled {
  background-color: transparent;
  cursor: not-allowed;
}
.project-image {
  max-width: 100%; /* Ensure the image doesn't exceed the container size */
  max-height: 100%; /* Ensure the image doesn't exceed the container size */
  object-fit: cover; /* Maintain aspect ratio and cover the container */
  border-radius: 5px; /* Optional: Add rounded corners to the images */
}

.image-container {
  width: 400px; /* Set a fixed width (adjust as needed) */
  height: 150px; /* Set a fixed height (adjust as needed) */
  overflow: hidden; /* Hide any overflowing content */
  display: flex;
  justify-content: center;
  align-items: center;
}
.left-button {
  left: 0;
  /* margin-left: 1rem; Position the "Previous" button to the left */
}

.right-button {
  right: 0;
  margin-right: 0rem; /* Position the "Next" button to the right */
}
.project-container:hover .nav-button {
  opacity: 1; /* Show buttons on hover */
}
.nav-button img {
  max-width: 100%;
  max-height: 100%;
}
.project-class h2{
  text-decoration: none;
}
.topic{
  text-decoration: none;
}
</style>
