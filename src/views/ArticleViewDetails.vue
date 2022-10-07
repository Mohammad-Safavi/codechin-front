<template>
  <div v-if="show_loading == 1" class="row w-100 mt-5">
    <div class="lds-heart m-auto"><div></div></div>
  </div>
  <div class="container mt-5">
    <div class="row">
      <div class="m-auto col col-lg-9 col-11">
        <img :src="post.pic_link" class="w-100 ar-pic-detail" />
        <div class="mt-5 mb-4">
          <h3>{{ post.title }}</h3>
          <p class="text-secondary">
            {{ post.user.first_name }} {{ post.user.last_name }} - تاریخ اخرین
            ویرایش :‌ {{ date }}
          </p>
        </div>
        <div class="mb-5">
          <p>{{ post.body }}</p>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import axios from "axios";
import moment from "moment";
export default {
  data() {
    return {
      post: "",
      date: "",
      show_loading : 0,
    };
  },
  methods: {
    get_list() {
      this.show_loading = 1
      axios
        .get(
          import.meta.env.VITE_API_DOMAIN +
            "api/v1/article/" +
            this.$route.params.id +
            "/"
        )
        .then((response) => {
          this.post = response.data;
          this.date = moment(response.data.updated_at).format(
            "YYYY-MM-DD | HH:mm"
          );
          this.show_loading = 0
        });
    },
  },
  beforeMount() {
    this.get_list();
  },
};
</script>