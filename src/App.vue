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
      <h1>Leezy Boost 103</h1>
      <CountDown />
     
    </section>
  </main>
</template>

<style lang="scss" scoped>
main {
  height: 100vh;
  width: 100%;
  background-image: url(./assets/images/landing.jpg);
  background-repeat: no-repeat;
  background-size: 385%;
  background-position-y: 37%;
  @media (min-width: 768px) {
    background-size: cover;
    background-position-y: initial;
  }
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
  letter-spacing: 0.15em;
}

p.logo-first {
  margin-right: 20px;
}
p.logo-second {
  margin-left: 20px;
}

.dropzone {
  position: absolute;
  bottom: 3%;
  left: 50%;
  transform: translateX(-50%);
  min-width: 300px;
  @media (min-width: 768px) {
    top: 37%;
    left: initial;
    right: 10.7%;
    transform: translateX(0);
  }
}

h1 {
  font-family: "Roboto", sans-serif;
  font-weight: 900;
  font-size: 24px;
  line-height: 1.67;
  letter-spacing: 0.15em;
  text-align: center;
  text-transform: uppercase;
  margin-bottom: 17px;

  @media (min-width: 768px) {
    font-size: 48px;
    line-height: 0.83;
    margin-bottom: 36px;
  }
}


</style>
