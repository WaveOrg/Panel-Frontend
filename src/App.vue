<template>
  <div id="app">
    <div id="loadingSpinnerBackground" v-if="this.$store.state.loading">
      <svg class="spinner" width="65px" height="65px" viewBox="0 0 66 66" xmlns="http://www.w3.org/2000/svg">
        <circle class="path" fill="none" stroke-width="6" stroke-linecap="round" cx="33" cy="33" r="30"></circle>
      </svg>
    </div>
    <div v-if="this.$store.state.alert.display" id="alertBox" uk-alert :class="`uk-alert-${this.$store.state.alert.type}`">
      <p>{{ this.$store.state.alert.message }}</p>
    </div>
    <router-view/>

    <script2 src="/js/uikit.min.js"></script2>
    <script2 src="/js/uikit-icons.min.js"></script2>
  </div>
</template>

<style>
@import url("../public/css/uikit.min.css");
@import url("../public/css/universal.css");

#alertBox {
  position: absolute;
  margin: auto;
  width: auto;
  max-width: 600px;
  margin-bottom: 20px;
  margin-right: 20px;
  z-index: 10000;
  bottom: 0px;
  right: 0px;
  word-wrap: break-word;
}

@media only screen and (max-width: 720px) {
  #alertBox {
    max-width: calc(100% - 80px);
  }
}

#loadingSpinnerBackground {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.6);
  display: -webkit-box;
  display: flex;
  -webkit-box-align: center;
  align-items: center;
  -webkit-box-pack: center;
  justify-content: center;
  z-index: 10000;
}
.spinner {
  -webkit-animation: rotator 1.4s linear infinite;
  animation: rotator 1.4s linear infinite;
}
@-webkit-keyframes rotator {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(270deg);
    transform: rotate(270deg);
  }
}
@keyframes rotator {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(270deg);
    transform: rotate(270deg);
  }
}
.path {
  stroke-dasharray: 187;
  stroke-dashoffset: 0;
  -webkit-transform-origin: center;
  transform-origin: center;
  -webkit-animation: dash 1.4s ease-in-out infinite, colors 5.6s ease-in-out infinite;
  animation: dash 1.4s ease-in-out infinite, colors 5.6s ease-in-out infinite;
}
@-webkit-keyframes colors {
  0% {
    stroke: #4285F4;
  }
  25% {
    stroke: #DE3E35;
  }
  50% {
    stroke: #F7C223;
  }
  75% {
    stroke: #1B9A59;
  }
  100% {
    stroke: #4285F4;
  }
}
@keyframes colors {
  0% {
    stroke: #4285F4;
  }
  25% {
    stroke: #DE3E35;
  }
  50% {
    stroke: #F7C223;
  }
  75% {
    stroke: #1B9A59;
  }
  100% {
    stroke: #4285F4;
  }
}
@-webkit-keyframes dash {
  0% {
    stroke-dashoffset: 187;
  }
  50% {
    stroke-dashoffset: 46.75;
    -webkit-transform: rotate(135deg);
    transform: rotate(135deg);
  }
  100% {
    stroke-dashoffset: 187;
    -webkit-transform: rotate(450deg);
    transform: rotate(450deg);
  }
}
@keyframes dash {
  0% {
    stroke-dashoffset: 187;
  }
  50% {
    stroke-dashoffset: 46.75;
    -webkit-transform: rotate(135deg);
    transform: rotate(135deg);
  }
  100% {
    stroke-dashoffset: 187;
    -webkit-transform: rotate(450deg);
    transform: rotate(450deg);
  }
}
</style>
