<template>
  <div id="app">
    <Header />
    <div class="team-container">
      <Team v-for="(team, index) in this.teams" :key="index" :teamName="team.teamName" />
    </div>
    <div class="new-team">
      <h2>Add New Team</h2>
      <input type="text" v-model="newTeam" />
      <button @click="createNewTeam">Create New Team</button>
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Team from "./components/Team.vue";

export default {
  name: "app",
  components: {
    Header,
    Team
  },
  data() {
    return {
      teams: [
        {
          teamName: "Gators"
        },
        {
          teamName: "Seminoles"
        }
      ],
      newTeam: ""
    };
  },
  methods: {
    createNewTeam() {
      const team = {
        teamName: this.newTeam
      };
      this.teams.push(team);
      this.newTeam = "";
    }
  }
};
</script>

<style>
body {
  margin: 0;
  background-color: #fa4616;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #fff;
}

.team-container {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
}
</style>
