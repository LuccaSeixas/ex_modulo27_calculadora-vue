<script setup>
import { reactive } from 'vue';


  const estado = reactive({
    num: '',
  })

  const insert = (num) => {
    estado.num += num;
  };

  const clear = () => {
    estado.num = '';
  };

  const back = () => {
    estado.num = estado.num.substring(0, estado.num.length -1);
  };

  const calc = () => {
    estado.num = eval(estado.num);
  };

</script>

<template>
  <div class="fundo">
    <h1>
      Calculadora criada com Vue.JS
    </h1>
    <div class="calculadora">
      <h2>
        Calculadora
      </h2>
      <p id="resultado">{{ estado.num }}</p>
      <table>
        <tr>
          <td><button class="botao" @click="clear()">C</button></td>
          <td><button class="botao" @click="back()"><</button></td>
          <td><button class="botao" @click="insert('/')">/</button></td>
          <td><button class="botao" @click="insert('*')">x</button></td>
        </tr>
        <tr>
          <td><button class="botao" @click="insert('7')">7</button></td>
          <td><button class="botao" @click="insert('8')">8</button></td>
          <td><button class="botao" @click="insert('9')">9</button></td>
          <td><button class="botao" @click="insert('-')">-</button></td>
        </tr>
        <tr>
          <td><button class="botao" @click="insert('4')">4</button></td>
          <td><button class="botao" @click="insert('5')">5</button></td>
          <td><button class="botao" @click="insert('6')">6</button></td>
          <td><button class="botao" @click="insert('+')">+</button></td>
        </tr>
        <tr>
          <td><button class="botao" @click="insert('1')">1</button></td>
          <td><button class="botao" @click="insert('2')">2</button></td>
          <td><button class="botao" @click="insert('3')">3</button></td>
          <td rowspan="2"><button id="botaoSpace" class="botao" @click="calc()">=</button></td>
        </tr>
        <tr>
          <td colspan="2" ><button id="botao0" class="botao" @click="insert('0')">0</button></td>
          <td><button class="botao" @click="insert('.')">.</button></td>
        </tr>
      </table>
    </div>
  </div>
</template>

<style scoped>
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    color: rgb(216, 210, 203);
  }

  body {
    margin: 0 !important;
}

  .fundo{
    height: 100vh;
    background-image: linear-gradient(180deg, rgb(7, 7, 46), hsl(229, 64%, 53%));
  }

  h1, h2{
    text-align: center;
  }

  .calculadora{
    background-color: rgb(17, 17, 17);
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    border-radius: 15px;
    padding: 20px 15px;
  }

  .botao{
    width: 50px;
    height: 50px;
    margin: 2px;
    font-size: 25px;
    background-color: rgb(46, 45, 45);
    cursor: pointer;
    border: none;
    border-radius: 5px;
  }

.botao:hover{
  background-color: rgb(0, 0, 0);
}

#botao0{
  width: 106px;
}

#botaoSpace{
  height: 106px;
}

#resultado{
  background-color: #fff;
  padding: 4px 4px 4px 0;
  margin: 12px 0;
  min-height: 36px;
  text-align: end;
  position: relative;
  top: 100%;
  color: black;
  font-size: 25px;
}

</style>
