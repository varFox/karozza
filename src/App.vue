<template>
  <div id="mainForm">
    <Form msg="все автомaгaзины тут"/>
  </div>
</template>

<script>
import Form from './components/Form.vue'

export default {
  name: 'mainForm',
  components: {
    Form
  }
}
</script>

<style>
main #mainForm {
  width: 100%;
  display: flex;
  justify-content: center;
  text-align: center;
  margin-top: 50px;
}
main #mainForm h1 {
  width: 100%;
  font-family: Merriweather, sans-serif;
  color: black;
  text-transform: uppercase;
  margin-bottom: 30px;
}
main label {
  color: black;
  font-family: Roboto;
  
}
</style>
