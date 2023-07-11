<template>
  <div class="hello">
    <div class="">
      <p class="text_etner_wrapp">{{text_enter}}</p>
    </div>
    <div class="text_result_wrapp">
      <p class="text">{{text_result}}</p>
    </div>
    <div class="btn_input">
      <button v-for="item in items" :key="item.id" :class="item.class" @click="item.func">{{item.type}}</button>
  </div>
  </div>
</template>

<script>
export default {
  name: 'HomePage',
  props: {
  },
  data() {
    return {
      items: [
        { id: 0, type: 'e', func: this.input.bind(this, 'e'), class: 'btn-1 btn' },
        { id: 1, type: 'h', func: this.input.bind(this, 'h'), class: 'btn-2 btn' },
        { id: 2, type: 'sin', func: this.input.bind(this, 'sin'), class: 'btn-3 btn' },
        { id: 3, type: 'deg', func: this.input.bind(this, 'deg'), class: 'btn-4 btn' },
        { id: 4, type: 'Ac', func: this.clear, class: 'btn-5 btn' },
        { id: 5, type: 'del', func: this.deleteLastCharacter, class: 'btn-6 btn' },
        { id: 6, type: '/', func: this.input.bind(this, '/'), class: 'btn-7 btn' },
        { id: 7, type: '*', func: this.input.bind(this, '*'), class: 'btn-8 btn' },
        { id: 8, type: '7', func: this.input.bind(this, '7'), class: 'btn-9 btn' },
        { id: 9, type: '8', func: this.input.bind(this, '8'), class: 'btn-10 btn' },
        { id: 10, type: '9', func: this.input.bind(this, '9'), class: 'btn-11 btn' },
        { id: 11, type: '-', func: this.input.bind(this, '-'), class: 'btn-12 btn' },
        { id: 12, type: '4', func: this.input.bind(this, '4'), class: 'btn-13 btn' },
        { id: 13, type: '5', func: this.input.bind(this, '5'), class: 'btn-14 btn' },
        { id: 14, type: '6', func: this.input.bind(this, '6'), class: 'btn-15 btn' },
        { id: 15, type: '+', func: this.input.bind(this, '+'), class: 'btn-16 btn' },
        { id: 16, type: '1', func: this.input.bind(this, '1'), class: 'btn-17 btn' },
        { id: 17, type: '2', func: this.input.bind(this, '2'), class: 'btn-18 btn' },
        { id: 18, type: '3', func: this.input.bind(this, '3'), class: 'btn-19 btn' },
        { id: 19, type: '=', func: this.calc, class: 'btn-20 btn' },
        { id: 20, type: '0', func: this.input.bind(this, '0'), class: 'btn-21 btn' },
        { id: 21, type: '.', func: this.input.bind(this, '.'), class: 'btn-22 btn' }
      ],

      text_enter: '',
      text_result: '0'
    }
  },  
  methods: {
    input(value) {
      this.text_enter += value;
    },

    calc() {
  const input = this.text_enter.trim();
  
  if (/[+\-*/]$/.test(input) || /^[+\-*/]/.test(this.text_result)) {
    this.text_result = 'Error';
  } else {
    this.text_result = eval(input).toString();
  }
},


    clear() {
      this.text_enter = '';
      this.text_result = '0';
    },

    deleteLastCharacter() {
      this.text_enter = this.text_enter.slice(0, -1);
    },
  }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@500&display=swap');

.hello {
  padding: 15px 25px;
  border-radius: 39px;
  background: linear-gradient(133deg, #F7F8FB 0%, rgba(247, 248, 251, 0.19) 100%);
  backdrop-filter: blur(51px);
  

.btn_input {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  grid-template-rows: repeat(5,62px);
  column-gap: 20px;
  row-gap: 16px;
  padding-bottom: 40px;
}

.btn:active {
  box-shadow: 0 0 5px #19acff;
}


.btn {
  border-radius: 20px;
  display: flex;
  padding: 6px 3px;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border: 1px solid white;
  color: white;
  font-family: 'Poppins';
  font-size: 32px;
  font-style: normal;
  font-weight: 500;
  line-height: normal;
}

.btn-7, .btn-8, .btn-12, .btn-16 {
  box-shadow: 0px 0px 9px 0px rgba(255, 255, 255, 0.43) inset;
  background: linear-gradient( #ADD8FF 0%,  #cee7ff 100%);
  border: none;
  color: #81c1fd;
}



.btn-20 {
  grid-column-start: 4;
  grid-row-start: 5;
  grid-row-end: 7;
  border-radius: 12px;
  background: #19ACFF;
  box-shadow: -9px 13px 23px 0px rgba(0, 163, 255, 0.65), -10px 4px 11px 0px #B0DFFF inset;
  color: #B2DAFF;
  border: none;
}

.btn-16 {
  grid-column-start: 4;
  grid-row-start: 4;
  grid-row-end: 5;
}
.btn-12 {
  grid-column-start: 4;
  grid-row-start: 3;
  grid-row-end: 4;
}
.btn-5 {
  grid-column-start: 1;
  grid-row-start: 2;
  grid-row-end: 3;
}

.btn-6 {
  grid-column-start: 2;
  grid-row-start: 2;
  grid-row-end: 3;
}

.btn-7 {
  grid-column-start: 3;
  grid-row-start: 2;
  grid-row-end: 3;
}

.btn-8 {
  grid-column-start: 4;
  grid-row-start: 2;
  grid-row-end: 3;
}

.btn-21 {
  grid-column-start: 1;
  grid-column-end: 3;
  grid-row-start: 6;
  grid-row-end: 7;
}

.text_etner_wrapp {
  height: 10px;
  color: #818181;
  font-family: 'Poppins';
  text-align: right;
  margin-right: 20px;
  margin-top: 70px;
  height: 10px;
}

.text_result_wrapp {
  width: 100%;
  height: 100px;
  color: #424242;
  font-family: 'Poppins';
  font-size: 48px;
  text-align: right;
}

.image-del {
  width: 30px;
  height: 30px;
}

@media screen and (max-width:450px) {
  .btn {
    font-size: 25px;
  }
}

}
</style>
