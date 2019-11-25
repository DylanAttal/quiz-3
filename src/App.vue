<template>
  <div id="app">
    <Header />
    <br />
    <div class="team-container">
      <Team
        v-for="(team, index) in this.teams"
        :key="index"
        :index="index"
        :teamName="team.teamName"
        :score="team.score"
        :addPoint="addPoint"
        :subtractPoint="subtractPoint"
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
    <Winner v-show="isWinnerModalVisible" />
    <div class="modal-overlay" v-show="isWinnerModalVisible"></div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Team from './components/Team.vue'
import Winner from './components/Winner.vue'

export default {
  name: 'app',
  components: {
    Header,
    Team,
    Winner
  },
  data() {
    return {
      teams: [
        {
          teamName: 'Gators',
          score: 0
        },
        {
          teamName: 'Seminoles',
          score: 0
        }
      ],
      newTeam: ''
    }
  },
  computed: {
    isWinnerModalVisible() {
      return this.teams.some(team => team.score > 7)
    }
  },
  methods: {
    createNewTeam() {
      const team = {
        teamName: this.newTeam
      }
      this.teams.push(team)
      this.newTeam = ''
    },
    addPoint(index) {
      this.teams[index].score++
    },
    subtractPoint(index) {
      this.teams[index].score--
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

.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(200, 200, 200, 0.5);
  z-index: 9;
}
</style>
