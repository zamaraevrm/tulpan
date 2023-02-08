<template>
  <div class="header">
    <div class="elements">
      <div class="element">
        НОВОСИБИРСК
        ул. Ленина, д. 3
      </div>
      <div class="element">
        C 10:00 до 22:00
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
  padding: 50px;
  pointer-events: none;
}
body {
  margin: 1%;
  background-color: #F09D9D;
}
.header {
  border-radius: 15px;
  width: 100%;
  background-color: #FFDBF3;
  display: table;
}
.mainblock {
  display: flex;
  margin-top: 5%;
}

.elements {
  align-items: center;
  display: flex;
  justify-content: space-around;
  margin-top:1.5%;
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
  margin: 5%;
  width: 50%;
  z-index: 1;
}
.app {
  margin: 5%;
  width: 50%;
  z-index: 0;
}

@media (max-width: 800px){
  .header{
    width: auto;
    margin: 15px;
    border-radius: 15px;
  }
  .elements{
    font-size: 16px;
  }
  .element:last-child{
    float:left;
  }
  .element:nth-child(3){
    float: bottom;
  }
  .ticket{
    width: auto;
    margin-bottom: 15px;
  }
  .app{
    width: auto;
  }
  .mainblock{
    display: block;
    margin: 15px;
  }
}

@font-face {
  font-family: TTCommons Regular;
  src: url(../src/fonts/TTCommons/TTCommons-Regular.ttf);
}
</style>