<template>
  <div class="container mt-5">
    <div class="row">
      <div v-for="x in list" :key="x.id" class="col-sm-4 mb-3">
        <div class="card">
          <img :src="x.pic_link" class="card-img-top ar-card" alt="..." />
          <div class="card-body">
            <h5 class="card-title">{{ x.title }}</h5>
            <p class="card-text">
              {{ x.body }}
            </p>
            <a href="#" class="btn btn-primary">مطالعه مقاله</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data() {
    return {
      list: "",
    };
  },
  methods: {
    get_list() {
      axios
        .get(import.meta.env.VITE_API_DOMAIN + "api/v1/article/list")
        .then((response) => {
          this.list = response.data;
        });
    },
  },
  mounted() {
    this.get_list();
  },
};
</script>