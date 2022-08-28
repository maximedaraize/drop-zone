<script setup>
import { ref, computed, onMounted } from "vue";

// init variables
const date = ref(new Date("10/12/2022")); // first match of the season (habs vs toronto)
const days = ref();
const hours = ref();
const minutes = ref();
const seconds = ref();
const timeArray = ref([]);
const timeText = ["days", "hours", "mins", "secs"];

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

// compare the date to the current date to see if the deadline is reached
const validDate = computed( ()=> {
  return Date.parse(date.value) > Date.parse(new Date());
})

</script>

<template>
<template v-if="validDate">
  <div class="digit-container">
    <div v-for="(time, index) in timeArray" :key="index" class="digit-wrapper">
      <div
        v-for="(digit, index) in [...time.toString()]"
        :key="index"
        class="digit-wrapper"
      >
        <template v-if="time.toString().length === 1"
          ><span class="digit">0</span><span class="digit">{{ digit }}</span>
        </template>
        <template v-else
          ><span class="digit">{{ digit }}</span></template
        >
      </div>
    </div>
  </div>
  <div class="text-container">
    <p
      v-for="(text, index) in timeText"
      :key="index"
      :class="`text text-${text}`"
    >
      {{ text }}
    </p>
  </div>
   <p class="detail">until drop</p>
  </template>
  <template v-else>
    <h2>Subscribe to our newsletter to never miss a drop</h2>
  </template>
</template>

<style lang="scss" scoped>
$digit-col-gap: 24px;

.digit-container,
.digit-wrapper,
.text-container {
  display: flex;
}
.digit-container,
.text-container {
  column-gap: calc(#{$digit-col-gap} / 2);
  @media (min-width: 768px) {
    column-gap: $digit-col-gap;
  }
}

.digit-wrapper {
  align-items: center;
  column-gap: calc(#{$digit-col-gap} / 4);
  @media (min-width: 768px) {
    column-gap: calc(#{$digit-col-gap} / 2);
  }
}

.digit {
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  font-family: "Rozha One", sans-serif;
  color: #fff;
  background: #000;
  width: 32px;
  height: 40px;
  font-size: 24px;
  line-height: 1.67;

  @media (min-width: 768px) {
    width: 58px;
    height: 73px;
    font-size: 48px;
    line-height: 40px;
    line-height: 0.83;
  }
}

.text-container {
  margin-top: 15px;
}

.text {
  width: 25%;
  text-align: center;
  font-family: "Roboto";
  font-size: 14px;
  line-height: 16px;
  font-style: normal;
  font-weight: 900;
  text-align: center;
  letter-spacing: 0.15em;
  text-transform: uppercase;

  @media (min-width: 768px) {
    font-size: 24px;
    line-height: 28px;
  }
}

h2 {
  font-family: "Roboto";
  font-size: 18px;
  line-height: 1.2;
  font-style: normal;
  font-weight: 900;
  text-align: center;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  width: 100%;
  max-width: 680px;

  @media (min-width: 768px) {
     font-size: 32px;
  }
}

p.detail {
  font-family: "Roboto", sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  line-height: 2.2;
  letter-spacing: 0.15em;
  text-align: center;
  text-transform: uppercase;
  margin-top: 18px;
  @media (min-width: 768px) {
    margin-top: 22px;
  }
}
</style>
