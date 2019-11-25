<template>
  <div id="app">
    <Header />
    <br />
    <div class="team-container">
      <Team
        v-for="(team, index) in this.teams"
        :key="index"
        :teamName="team.teamName"
      />
    </div>
    <br />
    <div class="new-team-wrapper">
      <div class="new-team">
        <b-form-group label="Add New Team">
          <b-form-input type="text" v-model="newTeam" />
        </b-form-group>
        <b-button variant="info" @click="createNewTeam"
          >Create New Team</b-button
        >
      </div>
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Team from './components/Team.vue'

export default {
  name: 'app',
  components: {
    Header,
    Team
  },
  data() {
    return {
      teams: [
        {
          teamName: 'Gators'
        },
        {
          teamName: 'Seminoles'
        }
      ],
      newTeam: ''
    }
  },
  methods: {
    createNewTeam() {
      const team = {
        teamName: this.newTeam
      }
      this.teams.push(team)
      this.newTeam = ''
    }
  }
}
</script>

<style>
body {
  margin: 0;
  background-color: #fa4616;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000;
}

.team-container {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
}

.new-team-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.new-team {
  width: 20%;
}
</style>
