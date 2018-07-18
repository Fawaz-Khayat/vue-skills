<template>
  <div class="hello">
    <!--
    <h1>{{ name }}</h1>
    
    {{ btnState ? 'The button is disabled' : 'The button is active'}}

    <button v-on:click="changeName" v-bind:disabled="btnState">Change Name</button>
    -->

    <ul>
      <li v-for="(data, index) in skills" :key="index"> {{ index }}. {{ data.skill }}</li>
    </ul>

    <p v-if="skills.length >= 1">You have more than 1 skills</p>
    <p v-else>You have less than or equal to 1 skill</p>
  </div>
</template>

<script>
export default {
  name: 'Skills',
  data() {
    return {
      name: 'Coursetro',
      btnState: true,
      skills: [
        { "skill" : "Vue.js" },
        { "skill" : "Front End Developer" },
      ]
    }
  },
  methods: {
    changeName: function() {

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style src="./Skills.css" scoped>
/*
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
*/


</style>
