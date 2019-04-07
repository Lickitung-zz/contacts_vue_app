<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div v-for="contact in contacts">
    <p>First Name: {{ contact.first_name }}</p>
    <p>Middle Name: {{ contact.middle_name }}</p>
    <p>Last Name: {{ contact.last_name}}</p>
    <p>Phone Number: {{ contact.phone_number }}</p>
    <p>Email: {{ contact.email }}</p>
    <hr>
    </div>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";

export default {
  data: function() {
    return {
      message: "Welcome to Vue.js!",
      contacts: []          
    };
  },
  created: function() {
    axios.get("/api/contacts").then(response => {
      this.contacts = response.data;
    });
  },
  methods: {}
};
</script>
