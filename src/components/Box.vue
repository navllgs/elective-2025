<template>
  <!-- html -->
   <div class="cell">
    {{ text }}
   </div>
</template>

<script>
export default {
  // js
  props: {
    text: {
      type: String
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