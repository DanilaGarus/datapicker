<template>

  <select v-model="yearValue" style="margin-right: 10px" @click="l">
    <option v-for="year in years" >
      {{ year }}
    </option>
  </select>

  <select v-model="monthValue" style="margin-right: 10px" @click="l">
    <option v-for="month in months">
      {{ month }}
    </option>
  </select>

  <select v-model="dayValue" style="margin-right: 10px" @click="l">
    <option v-for="date in dates" id="day">
      {{ date }}
    </option>
  </select>
</template>

<script>
import {ref} from 'vue';

const dayValue = ref('');
const monthValue = ref('');
const yearValue = ref('');
const dates = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31]
const months = [1, 2, 3, 4 , 5 , 6 , 7 , 8 , 9, 10, 11, 12]
const years = [2022,2021,2020,2019,2018]

let d = new Date();
let currentYear = d.getFullYear();
let currentMonth = d.getMonth();

export default {
  data() {
    return {
      dates,
      months,
      dayValue,
      monthValue,
      yearValue,
      years,
    }
  },
  methods:{
    l(){
      console.log(parseInt(dayValue.value))
     if((currentYear > yearValue.value))
       alert('Invalid year')

      if((currentMonth + 1) !== (parseInt(monthValue.value)))
        alert('Invalid month')

      if((parseInt(dayValue.value) >= 27) || (parseInt(dayValue.value) === 1))
        alert('Invalid day')
    }
  }
}
</script>
