<template>
  <div class="main">
    <div>Calendar normal <DatePicker color="teal" v-model="date" /></div>

    <div>Calendar range <DatePicker v-model="range" :disabled-dates='{ weekdays: semana }' is-range /></div>
    <div>
      DISABLE DATES IN SEMANA
      <div class="semana" v-for="(value,index) in week" :key="value">
        <input :id="index" :value="value.dia" v-model="checks" type="checkbox" />
        <label :for="index">{{value.dia}}</label>
      </div>
    </div>
  </div>
</template>

<script>
import { DatePicker } from "v-calendar";
export default {
  data() {
    return {
      valor: 0,
      date: new Date(),
      range: {
        start: null,
        end: null,
      },
      week: [
        { dia: "segunda" },
        { dia: "terça" },
        { dia: "quarta" },
        { dia: "quinta" },
        { dia: "sexta" },
        { dia: "sábado" },
        { dia: "domingo" },
      ],
      semana: [],
      checks:[],
    };
  },
  methods:{
    function(){
      print('oi')
    }
  },
  components: {
    DatePicker,
  },
};
</script>
<style scoped>
div {
  display: block;
  font-family: sans-serif "Hind";
  font-weight: bold;
}
.main {
  display: flex;
  width: 100%;
  height: 50vh;
  justify-content: space-around;
}
.semana{
  display: flex;
  width: 50%;
  justify-content: space-between;
}
input:checked{
    margin-left: 25px;
  border: 1px solid blue;
}
::-ms-check {
    color: red;
    background: black;
    padding: 1em;
}
</style>