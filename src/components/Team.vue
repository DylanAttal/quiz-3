<template>
  <div>
    <h1>{{ teamName }}</h1>
    <p>Update Team Name</p>
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
      teamScore: 0
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

<style>
</style>