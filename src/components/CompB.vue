<template>
  <div class="hello">
    Dette er komponent B
    <br>
    <input type="text" v-model="person.name" placeholder="Navn">
    <br>
    <input type="text" v-model="person.birthYear" placeholder="Fødselsår">
    <br>
    <button @click="toCompA()">Lagre og gå til komponent A</button>
  </div>
</template>

<script>
export default {
  name: "CompB",
  props: ["personprop"],
  data() {
    return {
      person: {
        name: null,
        birthYear: null
      }
    };
  },
  created: function() {
    this.person.name = this.personprop.name;
    this.person.birthYear = this.personprop.birthYear;
  },
  methods: {
    toCompA: function() {
      this.$emit("datachanged", this.person);
      this.$router.push("/");
    }
  }
};
</script>

<style scoped>
</style>
