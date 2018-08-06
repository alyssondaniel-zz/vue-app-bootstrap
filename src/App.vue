<template>
  <div id="app">
    <div v-for="message in messages" :key="message.id">
      <h4>{{ message.title }}</h4>
      <p>{{ message.text }}</p>
      <p>{{ message.timestamp }}</p>
    </div>
  </div>
</template>

<script>
import Firebase from 'firebase'
// Initialize Firebase
let config = {
  apiKey: 'AIzaSyA6pY0Wk6LOEcKvNTZWnSjsp6avL_LpeHw',
  authDomain: 'vue-app-97774.firebaseapp.com',
  databaseURL: 'https://vue-app-97774.firebaseio.com',
  projectId: 'vue-app-97774',
  storageBucket: 'vue-app-97774.appspot.com',
  messagingSenderId: '732395465798'
}

let app = Firebase.initializeApp(config)
let db = app.database()
let messagesRef = db.ref('messages')

export default {
  name: 'app',
  firebase: {
    messages: messagesRef
  }
}
</script>
