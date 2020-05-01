<template>
  <div class="add-log">
    <form @submit.prevent="logPoop">
      <input type="date" name="poopDate" :value="getNow('date')" />
      <input type="time" name="poopTime" :value="getNow('time')" />
      <textarea
        name="notes"
        id="notes"
        cols="30"
        rows="10"
        v-model="notesText"
      ></textarea>
      <button type="submit">Log a 💩</button>
    </form>
  </div>
</template>

<script>
import axios from 'axios';

axios.defaults.headers.post['Content-Type'] =
  'application/x-www-form-urlencoded';

export default {
  name: 'AddLog',
  data() {
    return {
      timestamp: [],
      notesText: null,
      notes: []
    };
  },
  methods: {
    getNow: dateOrTime => {
      const today = new Date();
      const year = today.getFullYear();
      const month = (today.getMonth() + 1).toString().padStart(2, '0');
      const day = today
        .getDate()
        .toString()
        .padStart(2, '0');
      const date = `${year}-${month}-${day}`;

      const time = today.getHours() + ':' + today.getMinutes();
      return dateOrTime == 'date' ? date : time;
    },
    logPoop: event => {
      const poopDate = event.target.elements.poopDate.value;
      const poopTime = event.target.elements.poopTime.value;
      const poopNotes = event.target.elements.notes.value && [
        ...event.target.elements.notes.value.split(', ')
      ];

      axios.post('https://bajs-co.firebaseio.com/poops.json', {
        poop: true,
        poopDate,
        poopTime,
        poopNotes
      });
    }
  },
  created() {
    this.getNow();
  }
};
</script>
