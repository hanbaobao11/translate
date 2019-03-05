<template>
  <div id="translateOutput">
    <h2>{{translatedText}}</h2>
    
  </div>
</template>

<script>


export default {
  name: 'translateOutput',
  props:[
    "translatedText"
  ]
}
</script>

<style>
#translateOutput {
  margin-top:20px;
  /* border:1px solid rebeccapurple; */
  font-size: 48px;
  color:red;
 
}
</style>