<template>
  <div id="vin-template">
    <input id="VIN" class="vin" type="text" placeholder="Введите VIN-номер" v-model="saveVin">
    <input class="vin bottomVin" type="text" placeholder="Выберете категорию запчастей" v-model="saveCategory">
    <button class="btnNext" @click="saveInfo()">Далее</button>
    <label for="VIN">VIN-номер нужен для того, чтобы сотрудник магазина мог более точно подобрать нужные вам автозапчасти и сделать предложение как можно быстрее.</label>
  </div> 
</template>

<script>

export default {
  name: 'VIN',
  props: ['goNext'],
  data() {
    return {
      saveVin: '',
      saveCategory: ''
    }
  },
  methods: {
    saveInfo() {
      this.goNext({
        VIN: this.saveVin,
        category: this.saveCategory,
        formNumber: 1,
        stepNumber: 1
      })
    }
  }
}
</script>

<style scoped>
main #vin-template {
  text-align: left;
}
main #vin-template input {
  display: block;
  width: 370px;
  border: 1px solid #0F73E8;
  border-radius: 10px;
  height: 40px;
  margin-bottom: 20px;
  padding: 0 15px;
}
main #vin-template .bottomVin {
  display: inline-block;
  float: left;
}
main #vin-template #VIN {
  margin-top: 20px;
}
main #vin-template .btnNext {
  width: 125px;
  background-color: #fff;
  border: 1px solid #ababab;
  padding: 10px 6px;
  margin: 0px 20px;
  font-size: 14px;
  border-radius: 10px;
  margin-right: 45px;
  background-color: #0F73E8;
  display: inline-block;
  float: left;
  
  
}
main #vin-template .btnNext {
  color: #000;
  font-family: Roboto;
}
main #vin-template button {
  color: #fff;
}
main #vin-template label {
  width: 450px;
  color: #545454;
  font-family: Roboto;
  font-weight: 300;
  font-size: 16px;
  text-align: left;
}
</style>

