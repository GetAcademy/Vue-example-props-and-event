<template>
  <div class="hello">
    Dette er komponent A<br/>
    <input type="text" v-model="person.name" placeholder="Navn"/><br/>
    <input type="text" v-model="person.birthYear" placeholder="Fødselsår"/><br/>
    <button @click="toCompB()">Lagre og gå til komponent B</button>
  </div>
</template>

<script>
export default {
  name: "CompA",
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
  methods:{
    toCompB: function () {
      this.$emit("datachanged", this.person);
      this.$router.push('CompB');
    }
  }
};
</script>

<style scoped>
</style>
