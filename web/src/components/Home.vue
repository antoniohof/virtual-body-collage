<template>
<div>
  <div>HOME</div>
  <div id="stats"></div>
  <div id="info" style='display:none'>
  </div>
  <div id="loading" style='display:flex'>
    <div class="spinner-text">
      Loading
    </div>
    <div class="sk-spinner sk-spinner-pulse"></div>
  </div>
  <div id='main' style='display:none'>
    <video id="video" playsinline style="display: none;"></video>
    <canvas id="output"/>
  </div>
  <ul id="colors" style="display: none"></ul>
  <div class="footer">

    <div class="footer-menu">
      <i class="material-icons switch-camera">switch_camera</i>
      <i class="material-icons mask mode active">portrait</i>
      <i class="material-icons mode bokeh">blur_on</i>
      <i class="material-icons mode part-map">format_color_fill</i>
      <i class="material-icons high-accuracy">high_quality</i>
    </div>
  </div>
</div>
</template>

<script>
import { bindPage } from '@/assets/js/bodypix'

export default {
  mounted () {
    bindPage()
  },
  data () {
    return {
    }
  }
}
</script>

<style>
body {
      margin: 0;
      width: 100%;
    }

    .footer {
      position: fixed;
      left: 0;
      bottom: 0;
      width: 100%;
      color: black;
    }

    .footer-text,
    #colors {
      font-family: Arial, Helvetica, sans-serif;
    }

    #colors {
      margin: 0;
      padding: 0;
      list-style: none;
    }

    #colors li {
      margin: 0;
    }

    #colors .color {
      width: 50px;
      height: 1em;
    }

    #colors li div {
      display: inline-block;
    }

    .footer-menu {
      display: none;
    }

    /*
     *  The following loading spinner CSS is from SpinKit project
     *  https://github.com/tobiasahlin/SpinKit
     */
    .sk-spinner-pulse {
      width: 20px;
      height: 20px;
      margin: auto 10px;
      float: left;
      background-color: #333;
      border-radius: 100%;
      -webkit-animation: sk-pulseScaleOut 1s infinite ease-in-out;
      animation: sk-pulseScaleOut 1s infinite ease-in-out;
    }

    @-webkit-keyframes sk-pulseScaleOut {
      0% {
        -webkit-transform: scale(0);
        transform: scale(0);
      }

      100% {
        -webkit-transform: scale(1.0);
        transform: scale(1.0);
        opacity: 0;
      }
    }

    @keyframes sk-pulseScaleOut {
      0% {
        -webkit-transform: scale(0);
        transform: scale(0);
      }

      100% {
        -webkit-transform: scale(1.0);
        transform: scale(1.0);
        opacity: 0;
      }
    }

    .spinner-text {
      float: left;
    }

    /* mobile */
    @media only screen and (max-width: 850px) {
      .footer {
        height: 46px;
      }

      .footer-text {
        display: none;
      }

      #main {
        width: 100%;
        height: 100%;
        overflow: hidden;
      }
    }
</style>
