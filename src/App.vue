<template>
  <div id="app">
    <div class="wrapper">
      <Progress :percentage="percentage"></Progress>
    </div>
    <div class="add" @click="add">增加</div>
  </div>
</template>

<script>
import Progress from './components/Progress.vue'

export default {
  name: 'App',
  mounted() {
    // canvas = document.querySelector('.canvas');
    // context = canvas.getContext('2d');
  },
  components: {
    Progress,
  },
  data() {
    return {
      percentage: 0,
    }
  },
  methods: {
    add()  {
      this.percentage = this.percentage + 10;
    }
    // fit() {
    //   let gap = 13,
    //   shapeCanvas = document.createElement('canvas'),
    //   shapeContext = shapeCanvas.getContext('2d'),
    //   fontSize = 500,
    //   fontFamily = 'Avenir, Helvetica Neue, Helvetica, Arial, sans-serif';
    //   shapeCanvas.width = Math.floor(window.innerWidth / gap) * gap;
    //   shapeCanvas.height = Math.floor(window.innerHeight / gap) * gap;
    //   shapeContext.fillStyle = 'red';
    //   shapeContext.textBaseline = 'middle';
    //   shapeContext.textAlign = 'center';
    // },
  }
}
</script>

<style>
html, body {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
}
#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif; */
  /* -webkit-font-smoothing: antialiased; */
  /* -moz-osx-font-smoothing: grayscale; */
  /* text-align: center; */
  color: #2c3e50;
  /* margin-top: 60px; */
  width: 100%;
  height: 100%;
}
.wrapper {
  box-sizing: border-box;
  margin-top: 50px;
  padding-top: 92px;
  width: 100%;
  height: 175px;
  /* opacity: 0.56; */
  /* background: rgba(255,255,255,0.56); */
  background-color: red;
  border-radius: 35px;
  display: flex;
  justify-content: center;
}
.add {
  margin-top: 40px;
}
.element {
  width: 300px; height: 200px;
  position: absolute;
  left: 0; right: 0; top: 0; bottom: 0;
  margin: auto;
}
.search-box {
  display: inline-block;
  white-space: nowrap;
}
.search-input {
  width: 200px;
  height: 20px;
  padding: 9px 39px 9px 9px;
  border: 1px solid #ddd;
  line-height: 20px;
}
.search-input:focus {
  outline: none;
  border-color: #2ea7e0;
}
.search-btn {
  position: absolute;
  width: 20px;
  height: 20px;
  border: 9px solid #fff;
  background: #ddd url(./assets/download.png) no-repeat center;
  margin: 1px 0 0 -40px;
}
.search-result {
  display: none;
}
.search-datalist {
  position: absolute; 
  width: 248px; 
  border: 1px solid #e6e8e9; 
  background-color: #fff;
  box-shadow: 0px 1px 2px #d5d7d8;
  text-align: left;
  z-index: 1;
}
.search-datalist > a {
  display: block;
  line-height: 36px;
  padding-left: 12px;
  color: #5e5e5e;
  text-decoration: none;
}
.search-datalist a:hover {
  color: #000;
  background-color: #f9f9f9;
}
.search-input:focus ~ .search-result {
  display: block;
}
.nav {
  display: table;
  table-layout: fixed;
  width: 100%;
  max-width: 600px;
  margin: 1em auto;
  background-color: #333;
  text-align: center;
}
.nav-list {
  display: table-cell;
  font-weight: 400;
}
.nav-a {
  display: block;
  line-height: 20px;
  padding: 20px;
  color: #bbb;
  text-decoration: none;
}
.nav-a:hover {
  color: #fff;
}
.icon-hot {
  position: absolute;
  width: 28px; height: 11px;
  margin: -6px 0 0 2px;
  background: url(./assets/hot.gif);
}
.top1 {
  position: absolute;
}
.tooltip-wrapper {
  width: 500px;
  line-height: 500px;
  text-align: center;
  background-color: #f0f3f9;
  margin: 0 auto;
}
.tooltip-wrapper > a {
  vertical-align: middle;
  text-decoration: none;
  line-height: 1;
}
.icon-delete {
  display: inline-block;  
}
.tips[data-title] {
  position: relative;
}
.tips[data-title]::before,
.tips[data-title]::after {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  visibility: hidden;
}
.tips[data-title]:hover::before,
.tips[data-title]:hover::after {
  transition: visibility .1s .1s;
  visibility: visible;
}
.tips[data-title]::before {
  content: attr(data-title);
  top: -33px;
  padding: 2px 10px 3px;
  line-height: 18px;
  border-radius: 2px;
  background-color: #333;
  text-align: left;
  color: #fff;
  font-size: 12px;
  white-space: nowrap;
}
.tips[data-title]::after {
  content: "";
  border: 6px solid transparent;
  border-top-color: #333;
  top: -10px;
}

/* .tooltip-wrapper */
.container {
  position: fixed;
  top: 0; right: 0; bottom: 0; left: 0;
  background-color: rgba(0, 0, 0, .5);
  text-align: center;
  overflow: auto;
  white-space: nowrap;
  font-size: 0;
}
.container:after {
  content: '';
  display: inline-block;
  height: 100%;
  vertical-align: middle;
}
.dialog {
  display: inline-block;
  vertical-align: middle;
  text-align: left;
  font-size: 14px;
  white-space: normal;
}
.dialog-content {
  width: 300px;
  height: 400px;
  background-color: #fff;
}
.box3 {
  display: inline-block;
  /* line-height: 0; */
  font-size: 0;
}
.box2 {
  text-align: justify;
  background-color: #f0f3f9;
  width: 320px;
  line-height: 0;
}
.justify-fix {
  display: inline-block;
  width: 96px;
  outline: 1px dashed;
} 
.box1 {
  background-color: #f0f3f9;
}
.box1 > img {
  height: 96px;
  margin-top: -999px;
}
.box {
  margin: 0 auto;
  background-color: #f0f3f9;
  line-height: 120px;
  width: 300px;
}
.content {
  line-height: 20px;
  display: inline-block;
  vertical-align: middle;
}
</style>
