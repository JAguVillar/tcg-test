<template>
  <Input @submit="log"></Input>
  <Cards ref="list" :query="query"></Cards>
</template>

<script>
import Input from "./Input.vue";
import Cards from "./Cards.vue";
export default {
  // Component data
  components: {
    Input,
    Cards,
  },
  data() {
    return {
      message: "Hello, Vue 3!",
      query: null,
    };
  },

  // Component methods
  methods: {
    // Your methods go here
    log(value) {
      this.$refs.list.log(value);
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
