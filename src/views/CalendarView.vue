<template>
  <div class="calendar-view">
    <div class="flex">
      <DayComponent v-for="day in days" :key="day" :text="day"></DayComponent>
    </div>
    <div v-for="week in 5" :key="week" class="flex">
      <DayComponent v-for="day in 7" :text="(day + ((week - 1) * 7) <= 31 ? day + ((week - 1) * 7) : '')"></DayComponent>
    </div>
    <div class="flex">
      <DayComponent v-for="day in days" :key="day" :text="day"></DayComponent>
    </div>
    <div class="flex">
      <SampleComponent></SampleComponent>
    </div>
    <!-- <div class="flex">
      <DayComponent v-for="day in 7" :text="day + 7"></DayComponent>
    </div>
    <div class="flex">
      <DayComponent v-for="day in 7" :text="day + 14"></DayComponent>
    </div>
    <div class="flex">
      <DayComponent v-for="day in 7" :text="day + 21"></DayComponent>
    </div>
    <div class="flex">
      <DayComponent v-for="day in 7" :text="day + 28"></DayComponent>
    </div> -->
  </div>
</template>

<script setup>
import DayComponent from '@/components/DayComponent.vue';
import SampleComponent from '@/components/Sample.vue';
import { defineComponent, ref } from 'vue';

defineComponent([DayComponent, SampleComponent])

const days = ref(['Sun', 'Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat'])

</script>

<style scoped>
.calendar-view {
  display: flex;
  flex-direction: column;
}

.flex {
  display: flex;
}
</style>