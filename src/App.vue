<template>
  <div id="app">
    <Navbar />
    <h2> {{ title }} </h2>
    <AllFriends :friends="friends" @delete="deleteFriend"></AllFriends>
    <OnlineFriends :friends="friends"></OnlineFriends>
    <hr>
    <Posts></Posts>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import AllFriends from './components/AllFriends.vue';
import OnlineFriends from './components/OnlineFriends.vue';
import Posts from './components/Posts.vue';

export default {
  name: 'App',
  // data method, it will return object
  data() {
    return {
      title: 'New Project :)',
      friends: [
        {name: 'Akash', isOnline: true},
        {name: 'Abir', isOnline: false},
        {name: 'Rahat', isOnline: true},
        {name: 'Fahim', isOnline: true},
        {name: 'Eshti', isOnline: false},
        {name: 'Aqib', isOnline: true},
        {name: 'Sumon', isOnline: false},
        {name: 'Nasim', isOnline: true},
        {name: 'Hasnat', isOnline: false}
      ]
    }
  },
  components: {
    Navbar,
    AllFriends,
    OnlineFriends,
    Posts,
  },
  methods: {
    deleteFriend(payload) {
      // console.log(payload)
      this.friends = this.friends.filter(friend => {
        return friend.name !== payload.name
      })
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
