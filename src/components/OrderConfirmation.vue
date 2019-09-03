<template>
<div id="order-confirmation-template">
  <h2>Подтверждение заказа</h2>
  <h3> {{form.detail}} </h3>
  <button class="addImg"><i class="fa fa-paperclip" aria-hidden="true"></i>{{ msg }}<input type="file" @change="imgUrl($event.target.value)" > </button>
  <div class="mmy">
    <span>Марка: </span><p> {{form.mark}} </p>
    <span>Модель: </span><p> {{form.model}} </p>
    <span>Год: </span><p> {{form.year}} </p>
  </div>
  <div class="vin">
    <span>VIN: </span><p> {{form.VIN}} </p>
  </div>
  
  <div class="personal-data">
    <span>Имя: </span><p> {{form.name}} </p>
    <span>Телефон: </span><p> {{form.tel}} </p>
    <span>E-mail: </span><p> {{form.email}} </p>
  </div>
</div>
</template> 

<script>
export default {
  name: 'Year',
  props: ['form', 'goNext'],
  data() {
    return {
      checkMore: false,
      msg: this.form.msg
    }
  },
  mounted() {
    this.getYear();
  },
  computed: {
    filteredYears() {
      return this.dataYears.filter(dataYear => {
        return dataYear.toString().indexOf(this.searchYear) !== -1
      })
    }
  },
  methods: {
    getYear() {
      fetch(this.src)
        .then(r => r.json())
        .then(json => {
          this.dataYears = json;
          
      });
    },
    showYears() {
      this.goNext({
        formNumber: 1
      });
    }
  }
}
</script>

<style scoped>
main #order-confirmation-template h2{
  font-family: Merriweather, sans-serif;
  color: #000;
  text-transform: uppercase;
  margin-bottom: 30px;
}
main #order-confirmation-template h3 {
  color: #000;
  display: flex;
}
main #order-confirmation-template .addImg {
  width: 205px;
  display: flex;
  background-color: #0067D7;
  color: #ffffff;
  border-radius: 7px;
  padding: 5px 8px;
  /* margin-left: 85px; */
  position: relative;
}
main #order-confirmation-template .addImg i {
  
  transform: rotate(85deg) translateX(3px);
  margin-right: 5px;
}
main input[type=file] {
  width: 205px;
  height: 30px;
  position: absolute;
  outline:0;
  opacity:0;
  top: 0;
  left: 0;
}
main #order-confirmation-template span {
  color: #000;
  display: inline-block;
  /* float: left; */
  font-family: Roboto;
  font-size: 18px;
  font-weight: 600;
  margin: 5px 0;
}
main #order-confirmation-template p {
  color: #000;
  display: inline-block;
  /* float: left; */
  font-family: Roboto;
  font-size: 18px;
  font-weight: 300;
  margin: 5px 30px 5px 5px;
}
main #order-confirmation-template .mmy {
  display: flex;
}
main #order-confirmation-template .personal-data {
  display: flex;
}
main #order-confirmation-template .vin {
  display: flex;
}
</style>