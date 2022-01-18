<template>
  <div class="about">
    <div class="main-title">
      <h1>coming soon</h1>
      <router-link class="btn btn-light" :to="'/'">Back</router-link>
    </div>
    <vue-particles
      color="#dedede"
      :particleOpacity="0.7"
      :particlesNumber="80"
      shapeType="circle"
      :particleSize="4"
      linesColor="#dedede"
      :linesWidth="1"
      :lineLinked="true"
      :lineOpacity="0.4"
      :linesDistance="150"
      :moveSpeed="3"
      :hoverEffect="true"
      hoverMode="grab"
      :clickEffect="true"
      clickMode="push"
    >
    </vue-particles>
  </div>
</template>
<style>
html,
body {
  height: 100%;
}
#app {
  height: 100%;
}
.about {
  position: relative;
  -ms-flex-align: center;
  -webkit-box-align: center;
  align-items: center;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  height: 100%;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
}
.main-title {
  color: #fff;
  z-index: 999;
}
.main-title h1 {
  font-size: 7rem;
  font-family: Teko, sans-serif;
  text-shadow: 8px 8px #000;
  text-transform: uppercase;
  margin: 0;
}
#particles-js {
  background-image: url(../assets/background/sky.jpg);
  background-size: cover;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
</style>
