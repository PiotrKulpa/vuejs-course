<template>
  <section>
  <h2>My Friends</h2>
  <ul>
    <friend-contact 
      v-for="friend in friends" 
      :key="friend.id"
      :id="friend.id" 
      :name="friend.name" 
      :phone-number="friend.phone" 
      :email-address="friend.email"
      @toggle-favorite="toggleFavoriteStatus"
      ></friend-contact>
  </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      friends: [
        {
          id: 'manuel',
          name: 'Manuel Lorenz',
          phone: '0123 4567 90',
          email: 'manuel@localhost.com'
        },
        {
          id: 'maria',
          name: 'Maria Lorenz',
          phone: '0555 4567 90',
          email: 'maria@localhost.com'
        }
      ]
    }
  },
  methods: {
    toggleFavoriteStatus(friendId) {
      console.log(friendId)
    }
  }
}
</script>   