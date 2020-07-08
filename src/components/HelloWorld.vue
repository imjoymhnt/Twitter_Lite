<template>
  <div class="hello">
    <h1>Tweet Me</h1>
    <div>
      <span> {{ len }} </span>
      <input type="text" v-model="tweet" :maxlength="charecter" @input="counter">
      <input type="submit" value="Tweet" @click="saveOntweets">
    </div>
    <div>
      <!-- <h4> {{ tweet }} </h4> -->
      <h4 v-for="(n, idx) in tweets" :key="idx"> {{ n }} </h4>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data(){
    return {
      charecter: 80,
      tweets: [],
      tweet: "",
      len: 0, 
    }
  },
  methods: {
    counter(){
      this.len =  this.charecter - this.tweet.length
      
    },
    saveOntweets(){
      // this.len = this.tweet.length
      this.tweets.push(this.tweet);
      this.tweet = "";
    },
    
    // letterCount(e){
    //   let typed = e.target.value.length
    //   this.count = this.count - typed      
    //   console.log(this.count);
      
    // }
  },
  props: {
    msg: String
  }
};
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
</style>
