<template>
  <Header />
  <router-view />
  <Footer />
</template>
<script>
import Header from '@/components/Layouts/Header.vue'
import Footer from '@/components/Layouts/Footer.vue'
export default {
  components : {
    Header,
    Footer
  }
}
</script>