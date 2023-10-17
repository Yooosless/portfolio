<template>

  <div class="main-container">
    <div class="contact-form">
      <h2>Send me a Message</h2>
      <form>
        <div class="form-group">
          <label for="name">Name:</label>
          <input type="text" id="name" name="name" required>
        </div>
        <div class="form-group">
          <label for="email">Email:</label>
          <input type="email" id="email" name="email" required>
        </div>
        <div class="form-group">
          <label for="message">Message:</label>
          <textarea id="message" name="message" rows="4" required></textarea>
        </div>
        <div class="form-group">
          <button type="submit">Send</button>
        </div>
      </form>
    </div>

    </div>
    <div class="social-links">
                    <div class="link">
                        <a href="https://github.com/Yooosless/" target="_blank">
                            <img src="../assets/github.png" alt="">
                            
                        </a>
                    </div>
                    <div class="link">
                        <a href="https://www.linkedin.com/in/shahid-afridi-2945481b7/" target="_blank">
                            <img src="../assets/linkedin.png" alt="">
                            
                        </a>
                    </div>
                    <div class="link">
                        <a href="https://twitter.com/Afridsh58054108" target="_blank">    
                            <img src="../assets/twitter.png" alt="">
                            
                        </a>
                    </div>
                    <div class="link">
                        <a href="https://www.reddit.com/user/chutiya_hoon" target="_blank">
                            <img src="../assets/reddit.png" alt="">
                           
                        </a>
                    </div>
            </div>
</template>

<script>

export default{

}
</script>

<style>

.form-group input{
  background-color: #fff;
}
.contact-form {
  margin: 20px auto;
  max-width: 100%;
  padding: 10px;
  border-radius: 8px;
  background-color: #fff;
  box-shadow: 0px 3px 16px rgba(0, 0, 0, 0.5);
color: black;
}


.form-group {
  margin-bottom: 20px;
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  
}

.contact-form h2 {
  text-align: center;
}
.form-group label {
  display: block;
  font-weight: bold;
  flex: 1; /* Distribute available space evenly among labels */
}
.form-group input,
.form-group textarea,
.form-group button {
  flex: 2; /* Distribute available space evenly among input elements and button */
}
.form-group input,
.form-group textarea {
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 16px;
  margin-right: 10px; /* Add some spacing between input elements */
}
.form-group button {
  background-color: #007bff;
  color: #fff;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}


.form-group button:hover {
  background-color: #0056b3;
}

.link a { 
  color: white; /* Set the text color to white */
  font-size: 10px;

}

.link img {
  height: 3rem; /* Reduce the height of the images */
  box-shadow: rgba(0, 0, 0, 0.5) 0px 3px 16px;
  /* Add margin to separate the links */
  margin-top:  0px;

}

.social-links {
  background-color: black;
  box-shadow: rgba(0, 0, 0, 0.5) 0px 3px 16px;

  display: flex;
  justify-content: space-evenly;
  height: 70px; /* Set the maximum height as needed */
  margin-top: 40px;
  padding-top: 20px;
}
.link {
  box-shadow: rgba(0, 0, 0, 0.5) 0px 3px 16px;
  padding-left: 5px;
  padding-right: 5px;
  justify-content: space-between;  

  
 /* Adjust the height of each link */
}

</style>