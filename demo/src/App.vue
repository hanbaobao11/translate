<template>
  <div id="app">
    <h1>在线翻译</h1>
    <h5 class="text-muted">简单/易用/便捷</h5>
    <translateForm v-on:form='translateText'></translateForm>
    <translateOutput v-text="translatedText"></translateOutput>

  </div>
</template>

<script>
import TranslateForm from './components/Translate'
import TranslateOutput from './components/TranslateOutput'

export default {
  name: 'App',
  data:function(){
    return{
      // output:''
      translatedText:''
     
    }
  },
  components: {
    TranslateForm,TranslateOutput
  
  },
  methods:{
    translateText:function(text,language){
      // alert(text)
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20190302T044812Z.2b8a354c09a019df.531d935d0d9428e27ca8aaf82072ffb26801bd9c&lang='+language+'&text='+text)
      .then((res)=>{
  console.log(res.body.text[0])
      this.translatedText=res.body.text[0];
})
    }
  }

}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
