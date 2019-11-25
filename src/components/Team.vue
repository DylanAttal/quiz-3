<template>
  <div>
    <h1>{{ newTeamName }}</h1>
    <label for="update-team-name">Update Team Name</label>
    <br />
    <input name="update-team-name" v-model="newTeamName" />
    <p>{{ teamScore }}</p>
    <button @click="addPoint">Add Point</button>
    <button @click="subtractPoint">Subtract Point</button>
  </div>
</template>

<script>
export default {
  name: "Team",
  props: {
    teamName: String
  },
  data() {
    return {
      teamScore: 0,
      newTeamName: this.teamName
    };
  },
  methods: {
    addPoint() {
      this.teamScore++;
    },
    subtractPoint() {
      this.teamScore--;
    }
  }
};
</script>

<style scoped>
</style>