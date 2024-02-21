<template>
<li>
  <h2>{{ name }}</h2>
  <button @click="toggleFavorite">Toggle</button>
  <button @click="toggleDetails">Show Details</button>
  <ul v-if="detailsAreaVisible">
    <li><strong>Phone:</strong>{{ phoneNumber }}</li>
    <li><strong>Email:</strong>{{ emailAddress }}</li>
  </ul>
</li>
</template>

<script>
export default {
  props: {
    id: {
      type: String,
      required: true
    },
    name: {
      type: String,
      required: true
    },
    phoneNumber: {
      type: String,
      required: true
    },
    emailAddress: {
      type: String,
      required: true
    },
  },
  data() {
    return {
      detailsAreaVisible: false,
   
    }
  },
  methods: {
    toggleDetails() {
      this.detailsAreaVisible = !this.detailsAreaVisible;
    },
    toggleFavorite() {
      this.$emit('toggle-favorite', this.id);
    }
  }

}
</script>