<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-view :personprop="person" @datachanged="dataChanged"/>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      person: {
        name: "Terje",
        birthYear: 1975
      }
    };
  },
  name: "App",
  methods: {
    dataChanged: function(personFromComponent) {
      this.person.name = personFromComponent.name;
      this.person.birthYear = personFromComponent.birthYear;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
