<template>
  <div class="header">
    <div class="elements">
      <div class="element">
        НОВОСИБИРСК<br>
        ул. Ленина, д. 3
      </div>
      <div class="element">
        C 10:00 до 22:00<br>
        ежедневно
      </div>
      <div class="element">
        <img src="../src/assets/whatsapp.png"/>
        <img src="../src/assets/telegram.png"/>
      </div>
      <div class="element">
        +7 (905) 953-90-93
      </div>
    </div>
  </div>
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
*{
  margin: 0;
  padding: 0;
}
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
  pointer-events: none;
}
body {
  background-color: #F09D9D;
}
.header {
  border-radius: 15px;
  width: 100%;
  background-color: #FFDBF3;
  display: table;
  text-align:center;
}
.mainblock {
  margin-left: 10%;
  margin-right: 10%;
  display: flex;
  margin-top: 5%;
  margin-bottom: 5vh;
}
.elements {
  align-items: center;
  display: flex;
  margin:1vh;
  justify-content: space-around;
  font-family: TTCommons Regular;
  font-size:20px;
  color: #43290A;
}
.element {
  justify-content: center;
  border-right: 0px;
  display: inline-block;
}
.ticket {
  margin: 0 5% 0 5%;
  width: 50%;
  z-index: 1;
}
.app {
  margin: 0 5% 0 5%;
  width: 50%;
  z-index: 0;
}
/*Smartphone*/
@media (max-width: 420px){
  body{
    width: 100%;
    height: 100%;
  }
  .elements{
    flex-direction: column;
  }
  .element:first-child{
    font-size: 26px;
  }
  .element:nth-child(2){
    font-size: 16px;
  }
  .header{
    display: block;
    margin: 15px;
    width: auto;
    margin-bottom: 15%;
    border-radius: 15px;
  }
  .ticket{
    width: 80%;
    margin-bottom: 15%;
    margin-right: auto;
    margin-left: auto;
  }
  .app{
    margin-right: auto;
    margin-left: auto;
    width: 80%;
  }
  .mainblock{
    display: block;
    margin: 15px;
  }
  .logotype{
    margin: 15px;
    width: auto;
    height: auto;
  }
}
/*Pad*/
@media (max-width: 820px) and (min-width: 420px){
  body{
    overflow:hidden;
    width: auto;
    height: 100vh;
  }
  .header{
    width: 100%;
    margin-top: 15px;
    border-radius: 15px;
  }
  .elements{
    font-size: 20px;
  }
  .ticket{
    height: 100%;
    width: auto;
    margin-bottom: 10%;
    margin-left: 5%;
    margin-right: 5%;
  }
  .app{
    height: 100%;
    width: auto;
    margin:0;
    margin-left: 5%;
    margin-right: 5%;
  }
  .mainblock{
    height: auto;
    display: block;
    margin: 5%;
  }
}

@font-face {
  font-family: TTCommons Regular;
  src: url(../src/fonts/TTCommons/TTCommons-Regular.ttf);
}
</style>