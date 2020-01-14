<template>
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
  <router-link to="Home"><a class="navbar-brand">Stock Trader</a></router-link>
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
      <router-link to="Portfolio" class="nav-link" tag="li"><a class="nav-link">End Day</a></router-link>
      <li class="nav-item nav-link dropdown">
        <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
          Save / Load
        </a>
        <div class="dropdown-menu" aria-labelledby="navbarDropdown">
          <a class="dropdown-item" href="#">Save Data</a>
          <a class="dropdown-item" href="#">Load Data</a>
        </div>
      </li>
    </ul>
    </form>
  </div>
</nav>
</template>