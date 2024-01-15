<template>
  <div class="relative main__container search">
    <input
      type="text"
      id="rounded-email"
      class="rounded-lg border-transparent flex-1 appearance-none border border-gray-300 w-full py-2 px-4 bg-white text-gray-700 placeholder-gray-400 shadow-sm text-base focus:outline-none focus:ring-2 focus:ring-purple-600 focus:border-transparent main__input"
      placeholder="Your email"
      v-model="query"
      @keyup.enter="log"
    />
  </div>
</template>

<script>
export default {
  // Component data
  data() {
    return {
      query: null,
    };
  },

  // Component methods
  methods: {
    // Your methods go here
    log() {
      console.log(this.query);
      this.$emit("submit", this.query);
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
