<template>
  <div class="profile">
    <div class="profile-header">
      <div class="profile-image">
        <img :src="profilePic" />
      </div>
      <div class="profile-info">
        <h2 class="profile-name">{{ personName }}</h2>
      </div>
    </div>
    <div class="profile-stats">
      Some of the stats that are specially intresting.
    </div>
    <div class="profile-settings">
      <h3>Settings</h3>
      <ul>
        <li>Edit profile</li>
        <li>Clear data</li>
        <li>Log out</li>
      </ul>
    </div>
  </div>
</template>

<script>
import people from '../../mock-data/people/index';

export default {
  name: 'Profile',
  data() {
    return {
      profilePic: people[0].personImg
    };
  },
  computed: {
    personName: () => `${people[0].personName} ${people[0].personSurname}`
  }
};
</script>
