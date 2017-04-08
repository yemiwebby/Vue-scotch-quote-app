<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="col-xs-12">
          <nav class="navbar navbar-default navbar-fixed-top">
            <div class="container">
              <ul class="nav navbar-nav navbar-center links">
                <li><router-link to="/"><i class="fa fa-home"></i> Quotes</router-link></li>
                <li><router-link to="/new-quote"><i class="fa fa-user"></i> New Quotes</router-link></li>
              </ul>
            </div>
          </nav>
        </div>
      </div>

      <div class="row">
        <div class="col-xs-12">
          <div id="view">
            <router-view></router-view>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script type="text/babel">
//  import NewQuote from './components/new-quote.vue';

export default {
  data () {
    return {

    }
  }

//  components: {
//    'app-new-quote': NewQuote
//  }
}
</script>

<style lang="scss">
#app {
  margin: 30px 0 0 0;
  background: #F7F8FB;
  min-height: 800px;
}

  #view {
    margin-top: 80px;
  }

  .navbar {
    background: #333333;
    min-height: 70px;
    font-weight: bold;
  }
  .links {
   margin-top: 10px;
  }

  .links li a {
    color: #ffffff !important;
    font-weight: bold;
    font-size: 20px;
  }
</style>
