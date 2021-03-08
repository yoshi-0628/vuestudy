<template>
  <div class="hello">
    <h1>Hello {{ name }}!!</h1>
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    <button @click="getFireStore">dad firestore</button>
    <button @click="signOut">Sign out</button>
  </div>
</template>

<script>
import firebase from 'firebase'

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      name: firebase.auth().currentUser.email,
      db: firebase.firestore().collection('users'),
      userName: ''
    }
  },
  computed: {
  },
  methods: {
    signOut: function () {
      firebase.auth().signOut().then(() => {
        this.$router.push('/signin')
      })
    },
    getFireStore: function () {
      const query = this.db.where('mail', '==', 'yoshihisa.drum@gmail.com')
        .get()
        .then((querySnapshot) => {
          querySnapshot.forEach((doc) => {
            return doc
          })
        })
        .catch((error) => {
          console.log('Error getting documents: ', error)
        })
      console.log(query)
    }
  }
}
</script>

<style scoped>
 /* 省略 */
</style>
