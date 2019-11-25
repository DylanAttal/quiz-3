<template>
  <div>
    <h1>{{ newTeamName }}</h1>
    <b-form-group label-for="update-team-name" label="Update Team Name">
      <b-form-input name="update-team-name" v-model="newTeamName" />
    </b-form-group>
    <p>{{ teamScore }}</p>
    <b-button variant="success" @click="addPoint">Add Point</b-button>
    <b-button variant="danger" @click="subtractPoint">Subtract Point</b-button>
  </div>
</template>

<script>
export default {
  name: 'Team',
  props: {
    teamName: String
  },
  data() {
    return {
      teamScore: 0,
      newTeamName: this.teamName
    }
  },
  methods: {
    addPoint() {
      this.teamScore++
    },
    subtractPoint() {
      this.teamScore--
    }
  }
}
</script>

<style></style>
