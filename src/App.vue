<template>
  <div class="header">
    <div class="elements">
      <div class="element1">
        НОВОСИБИРСК<br>
        ул. Ленина, д. 3
      </div>
      <div class="element2">
        C 10:00 до 22:00<br>
        ежедневно
      </div>
      <div class="element3">
        <img src="../src/assets/whatsapp.png"/>
        <img src="../src/assets/telegram.png"/>
        
      </div>
      <div class="element4">
        +7 (905) 953-90-93
      </div>
    </div>
  </div><br>
  <div class="mainblock">
    <div class="ticket">
      <MainPage/>
    </div>
    <div class="app">
      <PhotoCarousel/> 
    </div>
  </div>
  <div class="logotype">
    <img src="../src/assets/logotype.png" class="unselectable" draggable="false"/>
  </div>  
  
</template>

<script>
import PhotoCarousel from './components/PhotoCarousel'
import MainPage from './components/MainPage'
export default {
  name: 'App',
  components: {
    PhotoCarousel,
    MainPage,
  },
  data() {
    return {
    }
  }
}
</script>


<style>
.unselectable {
  user-drag: none; 
  user-select: none;
  -moz-user-select: none;
  -webkit-user-drag: none;
  -webkit-user-select: none;
  -ms-user-select: none;
}
.logotype {
  padding: 0px;
  text-align: center;
}
.logotype img {
  display: inline-block;
  padding: 50px;
  pointer-events: none;
}
body {
  background-color: #F09D9D;
}

.header {
  background-color: #FFDBF3;
  height: 97px;
  display: table;
  width: 100%;
  
}
.mainblock {
  position: relative;
  display:flex;
  height:500px;
  margin-top:7%;
}
.ticket {
  margin-left:14%;
  margin-top:3%;
  z-index: 1;
  display:flex;
}
.app {
  margin-left:9%;
  z-index: 0;
}
.elements {
  display: flex;
  text-align: center;
  margin-top:1.5%;
  font-family: TTCommons Regular;
  font-size:20px;
  color: #43290A;
}
.element1 {
  border-right: 0px;
  align-items: center;
  display: inline-block;
}
.element2 {
  border-right: 0px;
  align-items: center;
  display: inline-block;
}
.element3 {
  border-right: 0px;
  align-items: center;
  margin-top:-10px;
  display: inline-block;
}
.element4 {
  border-right: 0px;
  align-items: center;
  display: inline-block;
  margin-top:10px;
}
@media screen and (max-width: 980px) {
  .header {
  background-color: #FFDBF3;
  height: 97px;
  display: table;
}
body {
  justify-content: center;
  margin-left:auto;
  width: 100vw;
  height: 100vh;
}
.mainblock {
  position: relative;
  display:block;
  height:500px;
  margin-top:7%;
  
  
}
.ticket {
  margin-top:3%;
  z-index: 1;
  display:flex;
  float:left;
}
.app {
  z-index: 0;
  float:left;
}
.elements {
  display: flexbox;
  text-align: center;
  margin-top:1.5%;
  font-family: TTCommons Regular;
  font-size:20px;
  color: #43290A;
}
.element1 {
  border-right: 0px;
  align-items: center;
  display: inline-block;
}
.element2 {
  border-right: 0px;
  align-items: center;
  display: inline-block;
}
.element3 {
  border-right: 0px;
  align-items: center;
  margin-top:-10px;
  display: inline-block;
}
.element4 {
  border-right: 0px;
  align-items: center;
  display: inline-block;
  margin-top:10px;
}
  
}
@font-face {
  font-family: TTCommons Regular;
  src: url(../src/fonts/TTCommons/TTCommons-Regular.ttf);
}
</style>