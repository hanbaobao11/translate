<template>
  <div class="row" id="translateForm">
    <div class>
      <form class action v-on:submit="formSubmit">
        <input class="inp" type="text" placeholder="请输入需要翻译的内容" v-model="textToTranslate" name id>
        <select name id="sel" v-model="language">
          <option value="en">English</option>
          <option value="ru">Russian</option>
          <option value="ko">Korean</option>
          <option value="ja">Janpenese</option>
        </select>
        <input type="submit" class='btn' value="翻译">
      </form>
    </div>
  </div>
</template>
<script>
export default {
  name: "translateForm",
  data: function() {
    return {
      textToTranslate: "",
      language: ""
    };
  },
  methods: {
    formSubmit: function(e) {
      // alert(this.textToTranslate);
      this.$emit("form", this.textToTranslate, this.language);
      e.preventDefault();
    }
  },
  created: function() {
    this.language = "en";
  }
};
</script>

<style>
.row {
  width: 80%;

  /* border: 1px solid red; */
  margin: 0 auto;
  display: flex;
  justify-content: center;
  align-items: center;
  line-height: 40px;
}
.inp {
  display: block;
  width: 300px;
  height: 30px;
  border: 1px solid #ddd;

}
#sel {
  display: block;
  margin-top:10px;
  width: 300px;
  height: 30px;
   padding: 0 5px;
  /* border: solid 1px #ccc; */
  background: #fcc;
}
.btn{
  background: #ccc;
  padding:5px 20px;
}
</style>