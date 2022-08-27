<script setup>
import {ref, onMounted} from "vue";

// first match of the season (habs vs toronto)
const date = ref(new Date("10/12/2022"))
const days = ref();
const hours = ref();
const minutes = ref();
const seconds = ref();
const timeArray = ref([])

onMounted(() => {
  function countdown() {
    // return date in milliseconds
    const currentDate = new Date();
    const timeUntileDrop = date.value - currentDate;
    console.log(date.value)
    console.log(currentDate)
    console.log(timeUntileDrop);
    return timeUntileDrop;
  }
  countdown();
});

</script>

<template>

</template>

<style scoped></style>

