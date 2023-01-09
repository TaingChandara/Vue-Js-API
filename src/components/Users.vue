<template>
  <div class="container">
    <h3>Indentities Users</h3>
    <table class="table">
  <thead>
    <tr>
      <th scope="col">UserId</th>
      <th scope="col">Id</th>
      <th scope="col">Title</th>
    </tr>
    </thead>
    <tbody>
      <tr v-for="user in users" v-bind:key="user.id">
        <th scope="row">{{ user.userId }}</th>
        <td>{{ user.id }}</td>
        <td>{{ user.title }}</td>
      </tr>
    </tbody>
    </table>
  </div>
  </template>
  
  <script>

  import axios from 'axios';

    export default {
      name: 'Users',
      data() {
        return {
          users: null,
        };
      },
      created : function(){
        axios
        .get('https://jsonplaceholder.typicode.com/albums')
        .then(res => {
          this.users = res.data;
        })
      }
    }
  </script>
  
  <style>
    h3 {
      margin-bottom: 5%;
    }
  </style>