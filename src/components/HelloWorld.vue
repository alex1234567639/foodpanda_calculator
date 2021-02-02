<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
      <div class="input-title">Name</div><br>
      <input class="input-content" type="text" placeholder="Last name" style="width:147px"> 
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
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
    font-weight: 600;
    margin-bottom: 10px;
    display: inline-block;
    color: rgb(17, 52, 122);
}
.input-content{
    margin-bottom: 20px;
    padding: 4px;
    outline: none;
    color: #333333;
    background-color: #eeeeee;
    border: 1px solid #dddddd;
    &:focus, &:hover{
        border: 1px solid #bbbbbb;
    }
}
</style>
