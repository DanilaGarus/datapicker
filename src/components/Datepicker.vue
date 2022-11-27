<template>
  <Datepicker v-model="date" :min-date="minDate" :max-date="maxDate" :clearable="false" highlight-disabled-days hide-offset-dates style="max-width: 150px"/>
</template>

<script>
import { ref, onMounted } from 'vue';

export default {
  setup() {

    const date = ref();
    const maxDate = new Date();
    const minDate = new Date();

    maxDate.setDate(maxDate.getDate() + 1);
    minDate.setDate(10);

    onMounted(() => {
      const startDate = new Date();
      const endDate = new Date(new Date().setDate(startDate.getDate()));
      date.value = [startDate, endDate];
    })

    return {
      date,
      maxDate,
      minDate,
    }
  },
}
</script>
