<template>
  <div class="hello">
    <span class="input-title">小計：</span>
    <input class="input-content" type="number" placeholder="請輸入小計" v-model="subtotal"> 
    <span class="input-title">外送費：</span>
    <input class="input-content" type="number" placeholder="請輸入外送費" v-model="shipping"> 
    <span class="input-title">優惠折扣：</span>
    <input class="input-content" type="number" placeholder="請輸入優惠折扣" v-model="discount"> 
    <br>
    <span class="input-title">單人價格：</span>
    <input class="input-content" type="number" placeholder="請輸入單人價格" v-model="personalPrice"> 
    <button class="submit-btn" type="button" @click="calculate">計算</button> 
    <div v-for="(item, index) in priceList" :key="index">
      <span class="originalPrice">原價：{{ item.original }}</span> -----> <span class="discountPrice">{{ item.discount }}</span>
    </div>
    <br>
    <button v-if="priceList.length > 0" class="reset-btn" type="button" @click="resetList">清除</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: function() {
    return {
      subtotal: null,
      shipping: null,
      discount: null,
      personalPrice: null,
      priceList: []
    }
  },
  methods: {
    calculate() {
      const original = this.personalPrice
      const total = parseInt(this.subtotal) + parseInt(this.shipping)
      console.log(total)
      const discount = ((total - this.discount)/this.subtotal)*this.personalPrice
      this.priceList.push({original:original, discount:discount})
      this.personalPrice = null
    },
    resetList() {
      this.priceList = []
    }
  }
}
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.input-title{
  font-size: 18px;
  font-weight: 600;
  margin-bottom: 10px;
  display: inline-block;
  color: rgb(17, 52, 122);
}
.input-content{
  font-size: 15px;
  height: 20px;
  width:140px;
  margin-bottom: 20px;
  margin-right: 20px;
  padding: 5px 10px;
  outline: none;
  color: #333333;
  background-color: #eeeeee;
  border: 1px solid #dddddd;
}
.input-content:hover, .input-content:focus{
  border: 1px solid #bbbbbb;
}
.submit-btn{
  width: 80px;
  height: 30px;
  color: white;
  font-size: 16px;
  background-color: rgb(19, 64, 153);
  border: 1px solid rgb(19, 64, 153);
  border-radius: 5px;
  margin-right: 20px;
}
.submit-btn:hover, .submit-btn:focus{
  cursor: pointer;
  background-color: rgb(54, 54, 199);
  transition-duration: .5s;
}
.originalPrice {
  font-size: 16px;
  margin-right: 20px;
}
.discountPrice {
  font-size: 16px;
  margin-left: 20px;
  color: red;
}
.reset-btn{
  width: 80px;
  height: 33px;
  color: white;
  font-size: 16px;
  color: rgb(19, 64, 153);
  background-color: white;
  border: 1px solid rgb(19, 64, 153);
  border-radius: 5px;
  margin-bottom: 20px;
}
.reset-btn:hover, .reset-btn:focus{
  cursor: pointer;
  background-color: rgb(238, 238, 238);
  transition-duration: .5s;
}
</style>
