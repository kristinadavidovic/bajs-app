<template>
  <div>
    <div id="navigation-main" class="navigation navigation--main">
      <ul>
        <li>
          <router-link to="/">Home</router-link>
        </li>
        <li v-if="isLoggedIn">
          <router-link to="/log-poop">Log</router-link>
        </li>
        <li v-if="isLoggedIn">
          <router-link to="/stats">Stats</router-link>
        </li>
        <li v-if="isLoggedIn">
          <router-link to="/profile">Profile</router-link>
        </li>
        <li v-if="!isLoggedIn">
          <router-link to="/login">Login</router-link>
        </li>
        <li v-if="!isLoggedIn">
          <router-link to="/register">Register</router-link>
        </li>
        <li>
          <router-link to="/about">About</router-link>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import firebase from 'firebase';

export default {
  name: 'navigation',
  data() {
    return {
      isLoggedIn: false,
      currentUser: false
    };
  },
  created() {
    if (firebase.auth().currentUser) {
      this.isLoggedIn = true;
      this.currentUser = firebase.auth().currentUser.email;
    }
  }
};
</script>
