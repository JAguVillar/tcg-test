<template>
  <!-- Your component template goes here -->
  <div class="grid grid-cols-2 gap-4 sm:grid-cols-3 lg:grid-cols-6">
    <div v-for="card in cards" :key="card.id">
      {{ card.name }}
      <img :src="card.images.small" alt="" srcset="" />
    </div>
  </div>
</template>

<script>
export default {
  // Component data
  props: {
    query: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      cards: [],
    };
  },

  // Component methods
  methods: {
    // Your methods go here
    async log(query) {
      try {
        const fetched = await this.fetchData(query);
        this.cards = fetched.data;
      } catch (error) {
        console.error("Error:", error);
      }
    },
    async fetchData(q) {
      const apiUrl = `https://api.pokemontcg.io/v2/cards?q=name:${q}&pageSize=10`;

      const response = await fetch(apiUrl);
      if (!response.ok) {
        throw new Error(`HTTP error! Status: ${response.status}`);
      }

      const data = await response.json();
      // Handle the data received from the API

      return data; // Return the data if needed
    },
  },

  // Component lifecycle hooks
  beforeCreate() {
    // Executed before the component is created
  },
  created() {
    // Executed after the component is created
  },
  beforeMount() {
    // Executed before the component is mounted to the DOM
  },
  mounted() {
    // Executed after the component is mounted to the DOM
  },

  // Component computed properties
  computed: {
    // Your computed properties go here
  },

  // Component watch options
  watch: {
    // Your watched properties go here
  },
};
</script>

<style scoped>
/* Your component styles go here */
</style>
