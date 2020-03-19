<template>
  <div id="app">
    <!-- <nav class="navbar navbar-expand navbar-dark bg-dark">
      <a href="#" class="navbar-brand">bezKoder</a>
      <div class="navbar-nav mr-auto">
        <li class="nav-item">
          <a href="/articles" class="nav-link">Articles</a>
        </li>
        <li class="nav-item">
          <a href="/add" class="nav-link">Add</a>
        </li>
      </div>
    </nav> -->
    <nav
      class="navbar navbar-expand-lg navbar-light"
      style="background-color: blueviolet;"
    >
      <a class="navbar-brand" href="#">Criscar</a>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarNavAltMarkup"
        aria-controls="navbarNavAltMarkup"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
        <div class="navbar-nav">
          <a class="nav-item nav-link active" href="/articles"
            >Articles <span class="sr-only">(current)</span></a
          >
          <a class="nav-item nav-link" href="/add">Add</a>
        </div>
      </div>
    </nav>

    <div class="container mt-3">
      <router-view />
    </div>
  </div>
</template>

<script>
export default {
  name: "app"
};
</script>
