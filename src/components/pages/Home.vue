<template>
  <div class="home">
    <v-calendar is-dark :attributes="attributes" />
    <h1>This is a home page.</h1>
    <navLink url="log-poop">Log</navLink>
  </div>
</template>

<script>
import axios from 'axios';
import NavLink from '../elements/NavLink';

export default {
  name: 'Home',
  components: {
    NavLink
  },
  data() {
    return {
      attributes: [],
      colors: [
        'red',
        'orange',
        'yellow',
        'teal',
        'blue',
        'indigo',
        'purple',
        'pink'
      ]
    };
  },
  methods: {
    eventColor: (min, max) => {
      return Math.floor(Math.random() * (max - min) + min).toString();
    }
  },
  created() {
    // prod
    // axios.post('https://bajs-co.firebaseio.com/poops.json', {
    // stag
    axios.get('https://bajs-co.firebaseio.com/poops.json').then(res => {
      const data = Object.entries(res.data);
      data.forEach(element => {
        this.attributes.push({
          key: element[0],
          highlight: element[1].poop && this.colors[this.eventColor(1, 8)],
          dates: element[1].poopDate
        });
      });
    });
  }
};
</script>
