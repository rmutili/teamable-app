<template>
  <div id="display-view">
    <h1>User profile</h1>
    <img :src="image" />

    <span>Name: </span><b id="name">{{ name }}</b>
    <hr />

    <span>Email: </span><b id="email">{{ email }}</b>
    <hr />

    <span>Interests: </span><b id="interests">{{ interests }}</b>
    <hr />

    <button @click="handleEditProfile">Update Profile</button>
  </div>

  <div id="edit-view">
    <h1>User profile</h1>
    <img :src="image" />

    <span>Name: </span>
    <input type="text" id="input-name" v-model="name" />
    <hr />

    <span>Email: </span>
    <input type="text" id="input-email" v-model="email" />
    <hr />

    <span>Interests: </span>
    <input type="text" id="input-interests" v-model="interests" />
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
      name: "Anna Smith",
      email: "anna.smith@example.com",
      interests: "Coding",
    };
  },
  methods: {
    handleEditProfile() {
      document.getElementById("edit-view").style.display = "block";
      document.getElementById("display-view").style.display = "none";
    },
    handleUpdateProfile() {
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
