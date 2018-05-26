<template>
  <section class="container">
    <div class="button b1" v-on:click="toggleCeiling()">
      <p>Ceiling</p>
    </div>
    <div class="button b2" v-on:click="toggleLamp()">
      <p>Lamp</p>
    </div>
  </section>
</template>

<script>

import axios from 'axios';

export default {
  data() {
    return {
      errors: []
    }
  },
  methods: {
    toggleCeiling: function () {
      console.log("cat");
      axios.post(`http://mickeymug.tplinkdns.com:8123/api/events/toggleCeilingLight`)
      .then(response => {})
      .catch(e => {
        this.errors.push(e)
      })
    },
    toggleLamp: function () {
      console.log("dog");
      axios.post(`http://mickeymug.tplinkdns.com:8123/api/events/toggleLamp`)
      .then(response => {})
      .catch(e => {
        this.errors.push(e)
      })
    }
  }

  // // Toggles Lamp
  // toggleCeiling() {
  //   axios.post(`http://mickeymug.tplinkdns.com:8123/api/events/toggleLamp`, {
  //     // body: this.postBody
  //   })
  //   .then(response => {})
  //   .catch(e => {
  //     this.errors.push(e)
  //   })
  // }

}
</script>

<style>

  .container {
    width: 100%;
    height: 100vh;
    display: flex;
  }

  .button {
    display: flex;
    width: 50%;
    height: 100%;
    justify-content: center;
    align-items: center;
    font-family: 'Dosis', sans-serif;
    color: #fff;
    font-size: 3em;
    cursor: pointer;
  }

  .button:hover {
    font-weight: 800;
  }

  .b1 {
    background-color: #4ea1d3;
  }

  .b2 {
    background-color: #e85a71;
  }
</style>
