<template>
  <div class="day-component">
    <span>
      {{ text }}
    </span>
  </div>
</template>

<script>
export default {
  props: {
    text: {
      type: String,
    }
  }
}
</script>

<style scoped>
.day-component {
  border: 1px solid red;
  padding: 10px;
  height: 80px;
  width: 80px;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>