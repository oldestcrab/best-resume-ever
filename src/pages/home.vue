<!--
 * @Description: 页面展示
 * @Author: oldestcrab
 * @Github:
 * @Date: 2019-05-06 15:19:24
 * @LastEditors: oldestcrab
 * @LastEditTime: 2019-09-18 14:12:58
 -->
<template>
<div class="home">
  <a href="https://github.com/salomonelli/best-resume-ever" target="_blank"><img style="position: absolute; top: 0; right: 0; border: 0;" src="https://camo.githubusercontent.com/38ef81f8aca64bb9a64448d0d70f1308ef5341ab/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f6769746875622f726962626f6e732f666f726b6d655f72696768745f6461726b626c75655f3132313632312e706e67" alt="Fork me on GitHub" data-canonical-src="https://s3.amazonaws.com/github/ribbons/forkme_right_darkblue_121621.png"></a>
  <div class="logo">
    <img src="../assets/logo.png" />
  </div>
  <h3 class="title">best-resume-ever</h3>
  <div class="previews">
    <div class="preview">
      <router-link v-bind:to="'/resume/color_1'">
        <div class="preview-wrapper">
          <img src="../assets/preview/resume-color_1.png" />
          <span>color_1</span>
        </div>
      </router-link>
    </div>
    <div class="preview">
      <router-link v-bind:to="'/resume/color_2'">
        <div class="preview-wrapper">
          <img src="../assets/preview/resume-color_2.png" />
          <span>color_2</span>
        </div>
      </router-link>
    </div>
    <div class="preview">
      <router-link v-bind:to="'/resume/material-dark'">
        <div class="preview-wrapper">
          <img src="../assets/preview/resume-material-dark.png" />
          <span>material-dark</span>
        </div>
      </router-link>
    </div>
    <div class="preview">
      <router-link v-bind:to="'/resume/left-right'">
        <div class="preview-wrapper">
          <img src="../assets/preview/resume-left-right.png" />
          <span>left-right</span>
        </div>
      </router-link>
    </div>
    <div class="preview">
      <router-link v-bind:to="'/resume/oblique'">
        <div class="preview-wrapper">
          <img src="../assets/preview/resume-oblique.png" />
          <span>oblique</span>
        </div>
      </router-link>
    </div>
    <div class="preview">
      <router-link v-bind:to="'/resume/black_1'">
        <div class="preview-wrapper">
          <img src="../assets/preview/resume-black_1.png" />
          <span>black_1</span>
        </div>
      </router-link>
    </div>
    <div class="preview">
      <router-link v-bind:to="'/resume/black_2'">
        <div class="preview-wrapper">
          <img src="../assets/preview/resume-black_2.png" />
          <span>black_2</span>
        </div>
      </router-link>
    </div>
    <div class="preview">
      <router-link v-bind:to="'/resume/side-bar-rtl'">
        <div class="preview-wrapper">
          <img src="../assets/preview/resume-side-bar-rtl.png" />
          <span>side-bar-rtl</span>
        </div>
      </router-link>
    </div>
    <div class="preview">
      <router-link v-bind:to="'/resume/left-right-rtl'">
        <div class="preview-wrapper">
          <img src="../assets/preview/resume-left-right-rtl.png" />
          <span>left-right-rtl</span>
        </div>
      </router-link>
    </div>
    <div class="preview">
      <router-link v-bind:to="'/resume/creative'">
        <div class="preview-wrapper">
          <img src="../assets/preview/resume-creative.png" />
          <span>creative</span>
        </div>
      </router-link>
    </div>
    <div class="preview">
      <router-link v-bind:to="'/resume/color_1'">
        <div class="preview-wrapper">
          <img src="../assets/preview/resume-color_1.png" />
          <span>color_1</span>
        </div>
      </router-link>
    </div>

  </div>
</div>
</template>

<script>
import Vue from 'vue';
export default Vue.component('resume', {
    name: 'app'
});
</script>

<style scoped>
.home {
  font-family: 'Roboto' !important;
}

.logo {
  text-align: center;
}

.logo img {
  height: 50px;
  margin-top: 40px;
}

.title {
  font-weight: normal;
  text-align: center;
  width: 100%;
  color: black;
  font-weight: 300;
  font-size: 30px;
  line-height: 110%;
  margin: 1.78rem 0 1.424rem 0;
  margin-top: 0px;
  margin-bottom: 40px;
}

.previews {
  width: 90%;
  margin-right: auto;
  margin-left: auto;
}

.preview {
  width: 180px;
  float: left;
  margin-left: 1.5%;
  margin-right: 1.5%;
  margin-bottom: 1.5%;
  box-shadow: 0 2px 2px 0 rgba(0, 0, 0, 0.14), 0 1px 5px 0 rgba(0, 0, 0, 0.12), 0 3px 1px -2px rgba(0, 0, 0, 0.2);
  height: 252px;
  overflow: hidden;
}

.preview-wrapper {
  position: relative;
  background: white;
}

.preview img {
  width: 100%;
  opacity: 0.5;
  filter: blur(1px);
}

.preview span {
  position: absolute;
  max-width: 100%;
  font-size: 24px;
  font-weight: 300;
  color: rgba(0, 0, 0, 0.75);
  width: 100%;
  text-align: center;
  display: inline-block;
  top: 50%;
  transform: translateY(-50%);
}
</style>
