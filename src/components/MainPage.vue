<template>
    <div class="root">
        <p style = "font-family: TTCommons DemiBold; font-size:32px;">Оставить заявку</p>
        <div class="form">
            <input v-model="name" placeholder="Введите имя" @input="toggleButton()"/><br>
            <input v-model="phone" type="tel" @input="toggleButton()" placeholder="+7(911) 111-11-11" v-maska data-maska="+7 (###) ###-##-##"/>
            <br>
            <button id="submitButton" @click="submit(), showmodal=true" disabled>Отправить</button>
        </div>
    </div>
    <div v-show="showmodal" class="modal-overlay">
      <div class="modal">
        <img class="check" src="../assets/galka.png" alt="" />
        <p class="modalHigh">Успешно!</p>
        <p class="modalDown">Ожидайте звонка по Вашей заявке!</p>
        <button @click="showmodal=false" style="font-size:15px; cursor:pointer; background-color: #F28787;">Вернуться</button>
      </div>
    </div>
</template>
<script>
import { vMaska } from "maska"
export default {
    name: 'MainPage',
    directives: { maska: vMaska },
    data () {
        return {
            name: "",
            phone: "",
            showmodal:false,
            // Telegram BOT
            token: "5976108366:AAH5mWzx7xjQWDfbeTXf2qQlVBvjd69lbbw",
            chatid: "5017781259",
            url: "https://api.telegram.org/bot",
        }
    },
    methods: {
        submit() {
            const fullText = `Имя: ${this.name}%0AНомер телефона:  %2B${this.phone}`
            this.axios.post(`${this.url}${this.token}/sendMessage?chat_id=${this.chatid}&text=${fullText}`)
        },
        toggleButton() {
            if (this.name && this.phone) {
                document.getElementById('submitButton').disabled = false;
                document.getElementById('submitButton').style = 'cursor: pointer;'
                document.getElementById('submitButton').style.background = '#F28787';
            }
            else
            {
                document.getElementById('submitButton').disabled = true;
                document.getElementById('submitButton').style = 'cursor: default;'
                document.getElementById('submitButton').style.background = '#FFBCBC';
            }
        }
    }
}
</script>
<style>
.modalHigh {
    font-family: TTCommons DemiBold;
    font-size: 40px;
}
.modalDown {
    font-family: TTCommons Regular;
    font-size: 20px;
}
.modal-overlay {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  display: flex;
  justify-content: center;
  background-color: #000000da;
}

.modal {
  text-align: center;
  background-color: white;
  height: 500px;
  width: 500px;
  margin-top: 10%;
  padding: 60px 0;
  border-radius: 20px;
}
.close {
  margin: 10% 0 0 16px;
  cursor: pointer;
}

.close-img {
  width: 25px;
  margin-right:0px;
}

.check {
  width: 150px;
}
.root {
    justify-content: center;
    flex-direction: column;
    align-items: center;
    display: flex;
    width:auto;
    height: 100%;
    background-color: #FFDBF3;
    border-radius: 15px;
    text-align:center;
}
input {
    /*width:466px;*/
    margin-bottom: 20px;
    height:40px;
    border-radius: 10px;
    border: 0px;
    /*padding-left: 15px;*/
    font-size: 22px;
    font-family: TTCommons Regular;
}
button {
    background-color: #FFBCBC;
    width:90px;
    height:45px;
    border:none;
    border-radius:10px;
    font-family: TTCommons Regular; 
    color:white;
    font-size:16px;
    cursor:default;
}
@font-face {
  font-family: TTCommons DemiBold;
  src: url(../fonts/TTCommons/TTCommons-DemiBold.ttf);
}
@font-face {
  font-family: TTCommons Regular;
  src: url(../fonts/TTCommons/TTCommons-Regular.ttf);
}
@font-face {
  font-family: TTCommons Light;
  src: url(../fonts/TTCommons/TTCommons-Light.ttf);
}
</style>