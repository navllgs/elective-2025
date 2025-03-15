<template>
  <div>
    <h1>{{ title }}</h1>
    <p>Computed Message: {{ computedMessage }}</p>
    <button @click="incrementCounter">Increment</button>
    <p>Counter: {{ counter }}</p>
    {{ content }}
  </div>
</template>

<script>
export default {
  name: "LifecycleExample",

  // Component props (received from parent)
  props: {
    initialCounter: {
      type: Number,
      default: 0
    },
    content: {
      type: String,
      default: 'Hello world'
    }
  },

  // Component's reactive data
  data() {
    return {
      title: "Vue 3 Lifecycle Hooks (Options API)",
      counter: this.initialCounter
    };
  },

  // Computed properties (cached based on dependencies)
  computed: {
    computedMessage() {
      return `Counter is at: ${this.counter}`;
    }
  },

  // Methods (functions used in the template or component logic)
  methods: {
    incrementCounter() {
      this.counter++;
    }
  },

  // Watchers (reactive listeners for data changes)
  watch: {
    counter(newVal, oldVal) {
      console.log(`Counter changed from ${oldVal} to ${newVal}`);
    },
    updateTitle(){
      this.title = 'New title'
    }
  },

  // Lifecycle Hooks

  // Called before the component is created (reactivity not available yet)
  beforeCreate() {
    console.log("beforeCreate: Component is initializing");
  },

  // Called after the component is created (reactivity is available)
  created() {
    console.log("created: Component has been created");
  },

  // Called before the component is mounted to the DOM
  beforeMount() {
    console.log("beforeMount: Component is about to be added to the DOM");
  },

  // Called after the component is mounted to the DOM
  mounted() {
    console.log("mounted: Component has been added to the DOM");
  },

  // Called before the component updates (when data changes)
  beforeUpdate() {
    console.log("beforeUpdate: Component is about to re-render");
  },

  // Called after the component updates (when data changes)
  updated() {
    console.log("updated: Component has re-rendered");
  },

  // Called before the component is unmounted (removed from the DOM)
  beforeUnmount() {
    console.log("beforeUnmount: Component is about to be destroyed");
  },

  // Called after the component is unmounted (removed from the DOM)
  unmounted() {
    console.log("unmounted: Component has been removed from the DOM");
  },

  // Called when an error is caught in the component or its children
  errorCaptured(err, vm, info) {
    console.error("errorCaptured: An error occurred", err, "in", vm, "info:", info);
    return false; // Prevents the error from propagating further
  }
};
</script>

<style scoped></style>
