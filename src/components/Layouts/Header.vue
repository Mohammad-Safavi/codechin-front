<template>
  <!-- <div class="container-fluid p-5 bg-primary text-white text-center">
    <h1>گروه توسعه برنامه سازی کدچین</h1>
    <ul class="nav justify-content-center mt-4">
      <li class="nav-item">
        <a class="nav-link text-white" href="#">خانه</a>
      </li>
      <li class="nav-item">
        <router-link to="/article" class="nav-link text-white" href="#">مقالات</router-link>
      </li>
      <li class="nav-item">
        <a class="nav-link text-white" href="#">تماس با ما</a>
      </li>
      <li class="nav-item">
        <a class="nav-link text-white" href="#">ثبت سفارش</a>
      </li>
    </ul>
  </div> -->
  <nav class="navbar navbar-expand-lg navbar-light bg-white p-3">
    <div class="container-fluid">
      <a class="navbar-brand" style="width:200px" href="#"><img style="object-fit:cover" class="w-100" src="@/assets/img/logo.jpeg" /></a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0 me-4 ms-4">
          <li class="nav-item">
            <router-link :to="{ name: 'home' }" class="nav-link me-2 ms-2" v-bind:class="this.$route.path == '/' ? 'active' : ''" aria-current="page" href="#">خــانـه</router-link>
          </li><li class="nav-item">
            <router-link :to="{ name: 'article' }" class="nav-link  me-2 ms-2" v-bind:class="this.$route.path == '/article' ? 'active' : ''" aria-current="page" href="#">مقــالات</router-link>
          </li><li class="nav-item">
            <a class="nav-link  me-2 ms-2" aria-current="page" href="#">تماس با ما‍</a>
          </li><li class="nav-item">
            <a class="nav-link  me-2 ms-2" aria-current="page" href="#">ثبت سفارش</a>
          </li>
        </ul>
        <form class="d-flex">
          <input
            class="form-control me-2"
            type="search"
            placeholder="چی میخوای...."
            aria-label="Search"
          />
          <button class="btn btn-outline-primary" type="submit">جستجو</button>
        </form>
      </div>
    </div>
  </nav>
</template>