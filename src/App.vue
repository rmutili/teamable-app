<template>
  <div id="display-view">
    <h1>User profile</h1>
    <img :src="image" />

    <span>Name: </span><b id="name"> Anna Smith</b>
    <hr />

    <span>Email: </span><b id="email">anna.smith@example.com</b>
    <hr />

    <span>Interests: </span><b id="interests">Coding</b>
    <hr />

    <button @click="handleEditProfile">Edit Profile</button>
  </div>

  <div id="edit-view">
    <h1>User profile</h1>
    <img :src="image" />

    <span>Name: </span>
    <input type="text" id="input-name" placeholder="Smith" />
    <hr />

    <span>Email: </span>
    <input type="text" id="input-email" placeholder="anna.smith@example.com" />
    <hr />

    <span>Interests: </span>
    <input type="text" id="input-interests" placeholder="Coding" />
    <hr />

    <button @click="handleUpdateProfile">Update Profile</button>
  </div>
</template>

<script>
import image from "./profile.jpeg";
export default {
  name: "App",
  data() {
    return {
      image: image,
    };
  },
  methods: {
    handleEditProfile() {
      var name = document.getElementById("name").textContent;
      var inputName = document.getElementById("input-name");
      inputName.value = name;

      var email = document.getElementById("email").textContent;
      var inputEmail = document.getElementById("input-email");
      inputEmail.value = email;

      var interests = document.getElementById("interests").textContent;
      var inputInterests = document.getElementById("input-interests");
      inputInterests.value = interests;

      document.getElementById("edit-view").style.display = "block";
      document.getElementById("display-view").style.display = "none";
    },
    handleUpdateProfile() {
      var updatedName = document.getElementById("input-name").value;
      var name = document.getElementById("name");
      name.textContent = updatedName;

      var updatedEmail = document.getElementById("input-email").value;
      var email = document.getElementById("email");
      email.textContent = updatedEmail;

      var updatedInterests = document.getElementById("input-interests").value;
      var interests = document.getElementById("interests");
      interests.textContent = updatedInterests;

      document.getElementById("edit-view").style.display = "none";
      document.getElementById("display-view").style.display = "block";
    },
  },
};
</script>

<style>
img {
  width: 320px;
  height: 270px;
  display: block;
  margin-bottom: 40px;
}

div {
  margin: 40px auto;
  width: 80%;
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
}

hr {
  width: 400px;
  margin: 25px 0;
}

button {
  width: 160px;
  font-size: 15px;
  height: 45px;
  border-radius: 5px;
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
}

button:hover {
  background-color: #5ef3d3;
  cursor: pointer;
}
input {
  width: 200px;
  font-size: 15px;
  padding: 10px;
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
}

#edit-view {
  display: none;
}

h1 {
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
}
</style>
