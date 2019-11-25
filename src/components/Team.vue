<template>
  <div>
    <h1>{{ newTeamName }}</h1>
    <b-form-group label-for="update-team-name" label="Update Team Name">
      <b-form-input name="update-team-name" v-model="newTeamName" />
    </b-form-group>
    <p>{{ score }}</p>
    <b-button variant="success" @click="addPoint(index)">Add Point</b-button>
    <b-button variant="danger" @click="subtractPoint(index)"
      >Subtract Point</b-button
    >
  </div>
</template>

<script>
export default {
  name: 'Team',
  props: {
    index: Number,
    teamName: String,
    score: Number,
    addPoint: Function,
    subtractPoint: Function
  },
  data() {
    return {
      newTeamName: this.teamName
    }
  }
}
</script>

<style></style>
