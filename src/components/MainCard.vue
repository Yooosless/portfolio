<template>
    <div class="wrapper">
      <div class="main-container">
        <div class="container-one">
          <!-- Profile Section -->
          <div class="profile">
            <img src="../assets/afridi.png" alt="">
            <h3>Shaik Shahid Afridi</h3>
            <p>Software Engineer</p>
          </div>
        </div>
  
        <div class="container-two">
          <!-- About Me and Tech Stack Sections -->
          <div class="about-me">
            <h1>About me</h1>
            <p>
              I am a curious human in general. I have tried my hand on video
              editing, Finance/Accounting, Making bots.
            </p>
          </div>
  
          <div class="technology-section">
            <h1>Tech Stack</h1>
            <div class="logos">
              <img src="../assets/javascript.png" alt="">
              <img src="../assets/java.png" alt="">
              <img src="../assets/python.png" alt="">
              <img src="../assets/rust.png" alt="">
            </div>
          </div>
  
          <!-- Button Container -->
          <div class="button-container">
            <div class="projects-button">
              <a href=""><h2>My projects</h2></a>
            </div>
            <div class="projects-button">
              <a href=""><h2>My Resume</h2></a>
            </div>
          </div>
  
          <!-- Education and Experience Sections (Same Row) -->
          <div class="education-experience">
          <div class="section-container">
            <div class="education-options">
              <h3>Education :</h3>
              <ul>
                <button><li @click="selectedOption = 'Masters'">Masters</li></button>
                <button><li @click="selectedOption = 'Bachelors'">Bachelors</li></button>
                <button><li @click="selectedOption = 'School'">School</li></button>
                <!-- Add more options as needed -->
              </ul>
            </div>

            <div class="education-result" v-if="selectedOption === 'Masters'">
              <h3>Master of Computer Application (MCA)</h3>
              <p>CBIT College, Hyderabad</p>
              <p>GPA: 7.5</p>
              <p>Year: 2020-2022</p>
            </div>
            <div class="education-result" v-else-if="selectedOption === 'Bachelors'">
              <h3>Bachelor in Commerce (B.Com)</h3>
              <p>Pulla Reddy Degree College</p>
              <p>GPA: 7.8</p>
              <p>Year: 2017-2020</p>
            </div>
            <div class="education-result" v-else-if="selectedOption === 'School'">
              <h3>State Board (MPC)</h3>
              <p>Kakatiya Vidya Niketan High School</p>
              <p>GPA: 7.3</p>
            </div>
          </div>
          <div class="section-container">
            <div class="experience-options">
              <h3>Experience :</h3>
              <ul>
                <!-- Add experience options here -->
              </ul>
            </div>
            <div class="experience-result">
              <!-- Display experience details here -->
            </div>
          </div>
        </div>
        <!-- Add more sections for other education or experience options -->
      </div>
    </div>
  </div>
</template>

  <script>
  export default {
    data() {
      return {
        selectedOption: 'Masters', // Default selected option
      };
    },
  };
  </script>
  
  <style scoped>
  .wrapper {
    display: flex;
    justify-content: center;
  }
  
  img {
    height: 20px;
  }
  
  .main-container {
    width: 100%;
    border-radius: 25px;
    display: flex;
    flex-direction: row;
    box-shadow: rgba(0, 0, 0, 0.5) 0px 3px 16px;
    margin-top: 5rem;
  }
  
  .container-one {
    padding: 2%;
    width: 30%;
    border-radius: 25px;
    color: rgb(0, 0, 0);
    box-shadow: rgba(0, 0, 0, 0.5) 0px 3px 16px;
  }
  
  .profile img {
    height: 15rem;
    width: 100%;
    border-radius: 100%;
  }
  
  .container-two {
    width: 70%;
    margin-left: 1%;
    border-radius: 25px;
    color: rgb(0, 0, 0);
  }
  
  .logos img {
    height: 3rem;
    margin: 1rem;
  }
  
  .projects-button a {
    text-decoration: none;
    color: rgb(0, 0, 0);
  }
  
  .projects-button {
    margin: 5px;
    padding: 5px;
    background-color: rgb(78, 132, 194);
    border-radius: 15px;
  }
  
  .button-container {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
  }
  
  @media only screen and (max-width: 450px) {
    .main-container {
      width: 90%;
    }
  }
  
  .education-options li.active {
    font-weight: bold;
    color: blue; /* Change the color as needed */
  }
  
  .education-options li {
    cursor: pointer;
    margin: 5px 0;
    margin-left: 10px;
  }
  
  .education-options ul {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-direction: column;
    width: 80%;
  }
  
  

.education-options {
  display: inline-block; /* Display education options inline */
  width: 48%; /* Each section takes 48% of the available width */
  margin-left: 41px;
padding-top: 0;
}

.experience-options {
  display: inline-block; /* Display experience options inline */
  width: 48%; /* Each section takes 48% of the available width */
  text-align: left;
  margin-left: 2%; /* Add some spacing between education and experience */
}

.education-result,
.experience-result {
  display: inline-block; /* Display result inline */
  width: 48%; /* Each result takes 48% of the available width */
  text-align: left;
}
/* Style for the result section */
.section-container {
  border-radius: 15px; /* Apply rounded corners */
  padding: 15px; /* Add some spacing within the containers */
  box-shadow: rgba(0, 0, 0, 0.5) 0px 3px 16px; /* Apply shadow to the containers */
  margin: 10px 0; /* Add margin between sections */
  display: flex;
  justify-content: center; /* Center items horizontally */
  align-items: center; /* Center items vertically */
  min-height: 200px; /* Set a minimum height for the sections */
  height: auto;
}


  </style>
  