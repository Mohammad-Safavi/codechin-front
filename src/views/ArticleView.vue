<template>
  <div class="container mt-5">
    <div class="row">
      <div v-for="x in list" :key="x.id" class="col-sm-4 col-12 mb-3">
        <div class="card">
          <img :src="x.pic_link" class="card-img-top ar-card" alt="..." />
          <div class="card-body">
            <h5 class="card-title">{{ x.title }}</h5>
            <p class="text-secondary">{{x.user.first_name}} {{x.user.last_name}}</p>
            <!-- <p class="card-text">
              {{ x.body }}
            </p> -->
            <router-link :to="{ name: 'article-details', params:{id: x.id}}" href="#" class="btn btn-primary">مطالعه مقاله</router-link>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="w-100 mb-5 mt-5">
      <nav aria-label="Page navigation example">
        <ul class="pagination justify-content-center">
          <li class="page-item">
            <a class="page-link" href="#" aria-label="Previous">
              <span aria-hidden="true">&laquo;</span>
            </a>
          </li>
          <li v-for="index in page_number" :key="index" v-bind:class = "(page == index)?'active':''" class="page-item" @click="change_page(index)"><a class="page-link" href="#">{{index}}</a></li>
          <li class="page-item">
            <a class="page-link" href="#" aria-label="Next">
              <span aria-hidden="true">&raquo;</span>
            </a>
          </li>
        </ul>
      </nav>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data() {
    return {
      list: "",
      page : "1",
      page_number : "",
      post_count : ""
    };
  },
  methods: {
    get_list() {
      axios
        .get(
          import.meta.env.VITE_API_DOMAIN + "api/v1/article/?page_size=9&page="+this.page
        )
        .then((response) => {
          this.list = response.data.results;
          this.post_count = response.data.count;
          this.page_number_set()
        });
    },
    change_page(index){
      this.page = index
      this.get_list()
    },
    page_number_set(){
      this.page_number = Math.ceil(this.post_count / 9)
      console.log(this.page_number)
      if(this.page_number == 0 ){
        this.page_number = 1
      }
    }
  },
  beforeMount() {
    this.get_list();
  },
};
</script>