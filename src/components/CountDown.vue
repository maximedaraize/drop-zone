<script setup>
import {ref, onMounted} from "vue";

// first match of the season (habs vs toronto)
const date = ref(new Date("10/12/2042"))
const days = ref();
const hours = ref();
const minutes = ref();
const seconds = ref();
const timeArray = ref([])

onMounted(() => {
  function countdown() {
    const currentDate = new Date();
    const timeUntileDrop = date.value - currentDate;

    // time component formula *miliseconds based*
    const secondsFormula = 1000;
    const minutesForumla = secondsFormula * 60;
    const hoursFormula = minutesForumla * 60;
    const daysFormula = hoursFormula * 24;

    days.value = Math.floor(timeUntileDrop / daysFormula);
    hours.value = Math.floor((timeUntileDrop % daysFormula) / hoursFormula);
    minutes.value = Math.floor((timeUntileDrop % hoursFormula) / minutesForumla);
    seconds.value = Math.floor((timeUntileDrop % minutesForumla) / secondsFormula);

    timeArray.value = [days.value, hours.value, minutes.value, seconds.value];
    return timeArray;
  }
  countdown();
  setInterval(countdown, 1000);
});

</script>

<template>
<div v-if="Date.parse(date) > Date.parse(new Date)">
    <div v-for="(time, index) in timeArray" :key="index">{{time.toString().length === 1 ? `0${time}` : time }}</div>
</div>
</template>

<style scoped></style>

