<template>
  <Header />
  <router-view />
</template>
<script>
import Header from '@/components/Layouts/Header.vue'
export default {
  components : {
    Header,
  }
}
</script>