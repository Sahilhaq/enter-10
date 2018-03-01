<template>
  <div>
    <nav class="navigation">
      <div class="container">
        <router-link to="/hello">
          <span class="title">
          <i class="fa fa-home"></i> Enter10
          </span>
        </router-link>
        <router-link to="/">
          <span class="search-control"  onclick="searchbox(1)">
            Search <a style="font-family:fontawesome;"></a>
          </span>
        </router-link>
      </div>
    </nav>
  </div>
</template>
