<template>
  <div>
    <h1>{{ teamName }}</h1>
    <p>Update Team Name</p>
    <p>Team Score</p>
    <button>Add One</button>
    <button>Subtract One</button>
  </div>
</template>

<script>
export default {
  name: "Team",
  props: {
    teamName: String
  }
};
</script>

<style>
</style>