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

    <p>These are the skills that you possesss.</p>
    <!-- Style binding
    <div v-bind:style="{ backgroundColor: bgColor, width: bgWidth, height: bgHeight }"></div>
     -->

    <!-- class binding using object
    <div v-bind:class="alertObject"></div> 
    -->

    <!-- class binding
    <div  v-bind:class="{ alert: showAlert, 'another-class': showClass }"></div> 
    -->

    <!-- 
    <p v-if="skills.length >= 1">You have more than 1 skills</p>
    <p v-else>You have less than or equal to 1 skill</p>
    -->


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
      ],
      bgColor: 'yellow',
      bgWidth: '100%',
      bgHeight: '30px',
      
      alertObject:{
        alert: true,
      },
      showAlert: true,
      showClass: true
    }
  },
  methods: {
    changeName: function() {

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  /** style from the written version of the course found at
   https://coursetro.com/posts/code/136/Vue-CSS-Tutorial---Class-and-Style-Binding
   **/
  .holder {
    background: #fff;
  }

  ul {
    margin: 0;
    padding: 0;
    list-style-type: none;
  }
  
  ul li {
    padding: 20px;
    font-size: 1.3em;
    background-color: #E0EDF4;
    border-left: 5px solid #3EB3F6;
    margin-bottom: 2px;
    color: #3E5252;
  }

  p {
    text-align:center;
    padding: 30px 0;
    color: gray;
  }

  .container {
    box-shadow: 0px 0px 40px lightgray;
  }

  /* Style binding
  .alert {
    background-color: yellow;
    width: 100%;
    height: 30px;
  }
  .another-class {
    border: 5px solid black;
  } */
  
/* Original style
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
