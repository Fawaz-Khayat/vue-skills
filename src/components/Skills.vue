<template>
  <div class="hello">
    <!--
    <h1>{{ name }}</h1>
    
    {{ btnState ? 'The button is disabled' : 'The button is active'}}

    <button v-on:click="changeName" v-bind:disabled="btnState">Change Name</button>
    -->

    <form @submit.prevent="addSkill">
      <input type="text" placeholder="Enter a skill you have.." v-model="skill" v-validate="'min:5'" name="skill">
      <transition name="alert-in" enter-active-class="animated flipInX" leave-active-class="animated flipOutX">
        <p class="alert" v-if="errors.has('skill')">{{ errors.first('skill') }}</p>
      </transition>
    </form>
    <ul>
      <transition-group name="list" enter-active-class="animated bounceInUp" leave-active-class="animated bounceOutDown">
        <li v-for="(data, index) in skills" :key="index"> {{ index }}. {{ data.skill }}</li>
      </transition-group>
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
  data() {
    return {
      //name: 'Coursetro',
      name: 'Skills',
      skill: '',
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

    },
    addSkill(){
      this.$validator.validateAll().then((result) => {
        if(result){
          this.skills.push({skill: this.skill});
          this.skill = '';
        }
      });
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  @import "https://cdn.jsdelivr.net/npm/animate.css@3.5.1";
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

    input {
    width: calc(100% - 40px);
    border: 0;
    padding: 20px;
    font-size: 1.3em;
    background-color: #323333;
    color: #687F7F;
  }
    .alert {
    background: #fdf2ce;
    font-weight: bold;
    display: inline-block;
    padding: 5px;
    margin-top: -20px;
  }
  
  .alert-in-enter-active {
    animation: bounce-in .5s;
  }
  .alert-in-leave-active {
    animation: bounce-in .5s reverse;
  }
  @keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
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
