<template>
  <head>
    <link
      rel="stylesheet"
      href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@24,400,0,0"
    />
  </head>
  <form class="user-data">
    <labeL class="your-name"><b>First Name</b></labeL>
    <input class="first-name" type="text" v-model="firstName"/>
    <labeL class="your-last-name"><b>Last Name</b></labeL>
    <input class="last-name" type="text" v-model="lastName" @click="toggleContent"/>
  </form>

  <div v-if="showContent">
    <p>Hello {{ firstName }}</p>
  </div>

  <footer>
    <div>
      You can check my
      <button class="buttonGit" @click="redirectGithub"><b>GitHub</b></button> here!
    </div>
  </footer>
</template>

<script>
export default {
  name: "App",
  data: () => {
    return {
      firstName: "",
      lastName: "",
      github: "https://github.com/Macribeiro",
      showContent: false,
    };
  },
  methods: {
    redirectGithub() {
      open(this.github);
    },
    toggleContent() {
      this.showContent = this.firstName !== "";
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.buttonGit {
  background-color: blueviolet;
  color: black;
  border: 1px;
  border-radius: 4px;
}

.user-data {
  display: flex;
  flex-direction: column;
  width: min-content;
}

:root {
  --white: #fff;
  --gray-100: #e1e1e6;
  --gray-300: #c4c4cc;
  --gray-400: #8d8d99;
  --gray-500: #7c7c86;
  --gray-600: #323238;
  --gray-700: #29292e;
  --gray-800: #202024;
  --gray-900: #121214;

  --green-300: #00b37e;
  --green-500: #00875f;
  --green-700: #015f43;

  --red-300: #f75a68;
  --red-500: #ab222e;
  --red-700: #7a1921;
}
</style>
