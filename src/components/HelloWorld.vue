<template>
  <div class="hello">

    <div class="ui left aligned container">

      <img style="width: 300px;margin-top: 15px" src="/static/img/news.svg">

      <h2 class="ibm" style="font-size: 50px; margin-top: 57px; font-weight: bold;">All News at one place</h2>

    </div>



    <div class="ui grid container">

      <div class="ten wide left aligned column" >

        <h3 class="ibm-type-semibold">RECENT</h3>
        <div v-for="article in articleData">
        <div class="ui fluid segment">

          <div class="ui grid">
            <div class="six wide column">

              <img style="width: 100%;" v-bind:src="article.urlToImage">
            </div>

            <div class="ten wide left aligned column">
              <h3 class="ibm"> {{article.title}}</h3>
              <span class="ibm-type-light">{{article.source.name}}</span><span class="ibm-type-light">Dec 29, 2017</span> <span class="ibm-type-light">18:02 IST</span>
              <p class="ibm-type-serif">{{article.description}}</p>
              <a class="ibm-type-semibold" target="_blank" v-bind:href="article.url">Read more...</a>
            </div>


          </div>


        </div>
        </div>






      </div>


      <div class="six wide left aligned column">
        TRENDING
        <div class="ui fluid">
          <div>
          <h3>Apple apologizes for not being clearer about slowing down</h3>
            <a href="https://startupbbsr.com">Read more...</a>

          </div>

          <div>
          <h3>Apple apologizes for not being clearer about slowing down</h3>
            <a href="https://startupbbsr.com">Read more...</a>

          </div>
          <div>
          <h3>Apple apologizes for not being clearer about slowing down</h3>
            <a href="https://startupbbsr.com">Read more...</a>

          </div>
          <div>
          <h3>Apple apologizes for not being clearer about slowing down</h3>
            <a href="https://startupbbsr.com">Read more...</a>

          </div>
        </div>

        TRENDING
        <div class="ui fluid">
          <div>
          <h3>Apple apologizes for not being clearerabout slowing down</h3>
            <a href="https://startupbbsr.com">Read more...</a>

          </div>

          <div>
          <h3>Apple apologizes for not being clearerabout slowing down</h3>
            <a href="https://startupbbsr.com">Read more...</a>

          </div>
        </div>

        TRENDING
        <div class="ui fluid">
          <div>
          <h3>Apple apologizes for not being clearerabout slowing down</h3>
            <a href="https://startupbbsr.com">Read more...</a>

          </div>

          <div>
          <h3>Apple apologizes for not being clearerabout slowing down</h3>
            <a href="https://startupbbsr.com">Read more...</a>

          </div>
        </div>
      </div>




    </div>
<div ui class="grid container">
    Made with Love by
  </div>

  </div>



</template>

<script>
  export default {
    name: 'HelloWorld',
    data () {
      return {
          articleData:{}
      }
    },
    methods:{
        fetch_articles(){
          this.$http.get('https://newsapi.org/v2/top-headlines?country=in&category=business&apiKey=77053730ff024682b1ed50eb49243626').then(response => {
            // get body data

            this.articleData = response.body.articles;
          }, response => {
            // error callback
          });
        }
    },

    mounted(){
        this.fetch_articles();
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1, h2 {
    font-weight: normal;
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
