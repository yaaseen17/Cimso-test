<template>
  <nav>
    <div class="nav-img">
      <img
        src="https://www.cimso.com/wp-content/uploads/2020/01/cimso-logo-300-transparent.png"
        width="150"
        height="53"
        alt="cimso hotel management software"
        loading="lazy"
      />
    </div>
    <div class="nav-link">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
  </nav>
  <router-view />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body {
  background: linear-gradient(
    135deg,
    rgba(56, 56, 56, 1) 0%,
    rgba(56, 56, 56, 1) 35%,
    rgba(0, 0, 0, 1) 100%
  );
  background-repeat: no-repeat;
}
nav {
  width: calc(100% - (0px * 2));
  top: 15px;
  margin-left: 0px;
  margin-right: 0px;
  height: 5em;
  border: 0;
  font-size: 18px;
  background-color: rgba(0, 0, 0, 0.49);
  box-shadow: 0em 0.11699999999999999em 0.653em 3px rgb(0 0 0 / 42%);
  z-index: 9999;
  position: fixed;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  height: 5em;
}
.nav-link {
  flex-direction: row-reverse;
  justify-content: space-between;
  flex-grow: 0;
  flex-shrink: 1;
  margin-right: 200px;
}

nav a {
  font-weight: bold;
  color: rgb(190, 215, 57);
  text-decoration: none;
}
nav a:hover {
  text-decoration: underline rgba(255, 255, 255, 0.75);
  color: rgba(255, 255, 255, 0.75);
}
.nav-img {
  align-items: center;
  flex-basis: auto;
  border: 0;
  font-size: 1em;
  margin-left: 20px;
}
nav a.router-link-exact-active {
  color: rgba(255, 255, 255, 0.75);
}
</style>
