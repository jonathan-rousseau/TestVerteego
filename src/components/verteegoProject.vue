<template>
  <div class="ip">
    <h1>Mon adresse ip est <span id='myIp'>{{this.ip}}</span></h1>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'verteegoProject',
  data(){
    return{
      ip: null,
      }
    },
  mounted(){
    axios
    .get('https://api.ipify.org')
    .then((reponse) => {
      this.ip = reponse.data
      console.log(reponse);
   });
  },
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
.ip{
  display: flex;
  justify-content: center;
  border: 1px solid red;
  text-align: center;
  width: 50%;
  }
  #myIp{
    color:red;
    font-weight: bold;
    }
</style>
