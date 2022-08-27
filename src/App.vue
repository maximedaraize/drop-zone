<script setup>
import CountDown from "./components/CountDown.vue";
</script>

<template>
  <main>
    <div class="logo">
      <p class="logo-first">Drop</p>
      <p class="logo-second">Zone</p>
    </div>
    <section class="dropzone">
      <h1>leezy bost 103</h1>
      <CountDown />
      <p class="detail">until drop</p>
    </section>
  </main>
</template>

<style scoped>
main {
  height: 100vh;
  width: 100%;
  background-image: url(./assets/images/landing.jpg);
  background-size: cover;
}

.logo {
  position: absolute;
  top: 32px;
  right: 29px;
  display: grid;
  row-gap: 9px;
}
.logo p {
  display: inline-block;
  width: fit-content;
  font-family: "Rozha One", sans-serif;
  color: #fff;
  background: #000;
  text-transform: uppercase;
  font-size: 36px;
  line-height: 1.11;
  padding-inline: 14px;
}

p.logo-first {
  margin-right: 20px;
}
p.logo-second {
  margin-left: 20px;
}

.dropzone {
  position: absolute;
  width: fit-content;
  top: 37%;
  right: 10.7%;
}

h1 {
  font-family: "Roboto", sans-serif;
  font-size: 48px;
  font-weight: 900;
  line-height: 0.83;
  letter-spacing: 0.15em;
  text-align: center;
  text-transform: uppercase;
}

p.detail {
  font-family: "Roboto", sans-serif;
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  line-height: 2.2;
  text-align: center;
  text-transform: uppercase;
}
</style>
