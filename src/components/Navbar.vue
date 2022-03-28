<template>
  <div class="nav-container">
   <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="50" height="50" fill="currentColor" class="bi bi-code-square" viewBox="0 0 16 16">
 <path class="st0" d="M89.7,256.1c-9.7-0.4-17.7-3-23.9-8c-1.2-0.9-4-3.8-5-5c-2.5-3.2-4.2-6.3-5.4-9.7c-3.5-10.6-1.7-24.4,5.2-39.6
	c5.9-13,15-25.9,30.9-43.8c2.3-2.6,9.3-10.3,9.4-10.3c0,0-0.4,0.7-0.8,1.5c-4.1,6.9-7.7,15.1-9.6,22.1c-3.1,11.3-2.7,21,1.1,28.6
	c2.6,5.2,7.1,9.7,12.2,12.2c8.9,4.4,21.9,4.7,37.8,1.1c1.1-0.3,55.3-14.6,120.4-32c65.1-17.3,118.4-31.5,118.4-31.5
	c0,0-151.3,64.7-229.8,98.3c-12.4,5.3-15.8,6.7-21.6,8.7C113.9,254.1,100.6,256.6,89.7,256.1z"/>
</svg>
    <nav class="nav">
        
      <li><router-link to="/">Home</router-link></li>
      <li><router-link :to="{ name: 'About'}">About</router-link></li>
      <li><router-link :to="{ name:'Login'}">Login</router-link></li>
      <li><router-link :to="{ name: 'Register'}">Register</router-link></li>
      <li><router-link :to="{  name:'Products'}">Products</router-link></li>
      <li><router-link :to="{  name:'Profile'}">Profile</router-link></li>
      <li><router-link :to="{ name: 'Contact'}">Contact</router-link></li>
      <li><router-link :to="{ name: 'Cart'}">Cart</router-link></li>
      <div v-if="showAdminBoard">
      <li><router-link :to="{ name: 'Admin'}">Admin Board</router-link></li>
      </div>
      <li><button class="btn" v-if="currentUser" @click="logOut">Logout</button></li>
    </nav>
  </div>
  <div class="menu-container">
    <button class="menu" type="button">
      <div class="bar"></div>
    </button>
  </div>
  <div class="mobile-nav">
    <nav class="m-nav">
        <li><router-link class="mobile" to="/">Home</router-link></li>
        <li><router-link class="mobile" :to="{ name:'About'}">About</router-link></li>
      <li><router-link class="mobile" :to="{ name:'Login'}">Login</router-link></li>
      <li><router-link class="mobile" :to="{ name: 'Register'}">Register</router-link></li>
      <li><router-link class="mobile" :to="{  name:'Products'}">Porducts</router-link></li>
      <li><router-link class="mobile" :to="{  name:'Profile'}">Profile</router-link></li>
      <li><router-link class="mobile" :to="{ name: 'Contact'}">Contact</router-link></li>
      <li><router-link class="mobile" :to="{ name: 'Cart'}">Cart</router-link></li>
    </nav>
  </div>
   <router-view />
</template>

<script>
export default {
   computed: {
    currentUser() {
      return this.$store.state.auth.user;
    },
  },
  methods: {
    logOut() {
      this.$store.dispatch('auth/logout');
      this.$router.push('/login');
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@100;300;400;500;700&display=swap');

*{
font-family: 'Roboto', sans-serif;
margin:0; padding:0;
box-sizing: border-box;
outline: none; border:none;
text-decoration: none;
transition: all .3s linear;
line-height: 1.5;
}
html{
font-size: 62.5%;
overflow-x: hidden;
scroll-behavior: smooth;
}

body {
background:#ffffff;
/* padding-left: 10rem;
padding-right: 10rem */
}

* {
  box-sizing: border-box;
}

.nav-container {
  padding: 3px;
  display: flex;
  align-items: center;
  justify-content: flex-start;
  margin-top: 0%;
  width: 100%;
  background:#000000;
  position: fixed;
  z-index: 10;
  transition: 0.3s ease-in-out;
  /* opacity: 0.5; */
}

.nav.scroll {
  background-color: blueviolet;
}
.nav-container svg {
  color: #fff;
  margin-left: 1rem;
}

.menu {
  display: block;

  width: 40px;

  cursor: pointer;

  outline: none;

  appearance: none;

  background: none;

  border: none;

  z-index: 99;
}

.menu .bar,
.menu:before,
.menu:after {
  content: "";

  display: block;

  width: 100%;

  height: 5px;

  margin: 0 auto 5px;

  background-color: var(--main-color);

  transition: 0.5s ease-in-out;
}

.menu.is-active:before {
  transform: rotate(45deg) translate(8px, 6px);
}

.menu.is-active:after {
  transform: rotate(-45deg) translate(8px, -6px);
}

.menu.is-active .bar {
  transform: translate(-25px, 0px);
  opacity: 0;
}

.nav {
  display: flex;
  justify-content: flex-end;
  width: 100%;
}
.scroll {
  background-color: #a1572f;
  color: #eef;
}

.nav a {
  text-decoration: none;
  font-weight: 500;
  font-size: 18px;
  font-weight: 900;
  color: #fff;
  transition: 200ms ease-in-out;
  padding: 20px;
}

nav a:hover {
  color: #1C86EE;
}

.mobile-nav {
  position: fixed;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  top: 0;
  right: -100%;

  background-color: rgba(0, 0, 0, 85%);
  width: 50%;
  height: 100%;
  z-index: 99;
  transition: 0.4s ease-in-out;
  box-shadow: 0px 0px 150px rgba(0, 0, 0, 0.7);
}

.m-nav {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  row-gap: 2rem;
}

.m-nav a {
  text-decoration: none;
  width: 100%;
  font-weight: 700;
  font-size: 1rem;
  color: #fff;
  transition: 200ms ease-in-out;
  padding: 10px;
}

.mobile-nav.is-active {
  position: fixed;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  top: 0;
  right: 0;
  height: 100%;
  transition: 0.4s ease-in-out;
}
@media only screen and (max-width: 770px) {
  .nav {
    display: none;
  }
  .nav-container {
    display: none;
    box-shadow: none;
    appearance: none;
    margin: 0;
    padding: 0;
  }

  .nav-container svg {
    color: #fff;
    width: 100px;
    margin-left: 1rem;
  }

  .menu-container {
    background-color: transparent;
    width: 100%;
    height: 80px;
    padding: 20px;
    position: fixed;
    top: 1%;
    display: flex;
    justify-content: flex-start;
    align-items: center;
    z-index: 6;
  }
}
@media only screen and (max-width: 2000px) and (min-width: 771px) {
  .menu {
    display: none;
  }
  .mobile-nav {
    display: none;
  }
}
</style>