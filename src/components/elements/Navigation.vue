<template>
  <div>
    <div
      v-if="navType === 'main'"
      id="navigation-main"
      class="navigation navigation--main"
    >
      <router-link v-for="link in navLinks" :key="link.id" :to="link.url">{{
        link.title
      }}</router-link>
    </div>
    <div
      v-if="navType === 'footer'"
      id="navigation-footer"
      class="navigation navigation--footer"
    >
      <router-link v-for="link in footerLinks" :key="link.id" :to="link.url">{{
        link.title
      }}</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'navigation',
  props: {
    navType: {
      required: true,
      type: String
    }
  },
  data() {
    return {
      navLinks: [
        {
          id: 0,
          url: '/',
          title: 'Home'
        },
        {
          id: 1,
          url: '/log-poop',
          title: 'Log POOP'
        },
        {
          id: 2,
          url: '/stats',
          title: 'Stats'
        },
        {
          id: 3,
          url: '/profile',
          title: 'Profile'
        }
      ],
      footerLinks: [
        {
          id: 0,
          url: '/about',
          title: 'About'
        }
      ]
    };
  }
};
</script>
