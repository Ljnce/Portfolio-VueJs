<template>
  <div id="test">
    <div class="container-title">
      <h1> Welcome to my test page </h1>
    </div>
    <p v-if="errors.length">
      <b>Please correct the following error(s):</b>
      <ul>
        <li v-for="(error, index) in errors" :key="index">{{ error }}</li>
      </ul>
    </p>
    <div class="container-push">
    <p>
      <label for="age">Age</label>
      <input
        id="age"
        v-model="test"
        type="number"
        name="age"
        min="0"
      >
    </p>
      <br>
      <button @click="numbers.push(test)"> Premi qui </button>
    </div>
    <div class="container-for" v-for="(number, index) in numbers" :key="index">
        <p> {{number}} </p>
    </div>
    <div class="error">
      <h1 @click="error"> NON CLICCARE QUI </h1>
    </div>
  </div>
</template>

<script>

  export default {
    name : "test",
    data () {
      return {
        numbers : [],
        errors: []
      }
    },
    methods: {
      errorCheck: function() {
        this.errors = [];
        if (!this.test) {
          this.errors.push("Name required.");
        }
      },
      error : function() {
        alert('Te lo avevo detto!');
      }
    }
  }

</script>

<style lang="scss">

#test {
  height: 500px;
  width: 100vw;
  display: flex;
  align-items: center;
  flex-direction: column;
  .error {
    h1 {
      &:hover {
        color: red;
        cursor: pointer;
      }
    }
  }
}

</style>
