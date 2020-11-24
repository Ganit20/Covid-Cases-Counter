<template>
      <div id="main">
         <div></div>
      </div>
</template>

<script>
const axios = require("axios");
export default {
  name: "App",
  data() {
    return {
      data: []
    };
  },
  beforeMount(){
    this.getName();
  },
  methods: {
    async getName(){
      const { data } = await axios.get("https://covid19-api.org/api/status");
      for(var i in data)
      this.data.push( data [i]);
      
      this.data.forEach(element=> {
          document.getElementById("main").innerHTML +="Country: " + element.country + "<BR>";
          console.log(element);
      });
   
    }
   
  }
};
</script>