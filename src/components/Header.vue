<template>
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
  <router-link to="/"><a class="navbar-brand">Stock Trader</a></router-link>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto">
      <router-link to="Portfolio" activeClass="active" class="nav-link" tag="li"><a class="nav-link">Portfolio</a></router-link>
      <router-link to="Stocks" activeClass="active" tag="li" class="nav-link"><a class="nav-link">Stocks</a></router-link>
    </ul>
    <form class="form-inline my-2 my-lg-0">
    <ul class="navbar-nav mr-auto">
      <li class="nav-link pointer"><a class="nav-link pointer" @click="endDay">End Day</a></li>
      <li class="nav-item nav-link dropdown">
        <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
          Save / Load
        </a>
        <div class="dropdown-menu" aria-labelledby="navbarDropdown">
          <a class="dropdown-item" href="#">Save Data</a>
          <a class="dropdown-item" href="#">Load Data</a>
        </div>
      </li>
      <li class="nav-item nav-link"><strong class="nav-link" style="color: white;">Funds: {{ funds | currency }}</strong></li>
    </ul>
    </form>
  </div>
</nav>
</template>

<script>
import {mapActions} from 'vuex';


  export default {
    computed: {
      funds(){
        return this.$store.getters.funds;
      }
    },
    methods: {
      ...mapActions([
        'randomizeStocks'
      ]),
      endDay() {
        this.randomizeStocks();
      }
    }
  }
</script>

<style scoped>
  .pointer{
    cursor: pointer;
  }

</style>