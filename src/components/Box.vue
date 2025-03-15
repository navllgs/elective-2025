<template>
  <!-- html -->
   <div>
     <div class="cell">
      {{ textData }}
     </div>
     <div>
      <button @click="changeText('text here...')">change text</button>
     </div>
   </div>
</template>

<script>
export default {
  // js
  props: {
    text: {
      type: String
    }
  },

  data() {
    return {
      // data
      textData: this.text
    }
  },

  methods: {
    changeText(textParams){
      this.textData = textParams
    }
  }
}
</script>

<style>
/* styles */
.cell {
  padding: 8px;
  color: black;
  border: 1px solid red;
}
</style>