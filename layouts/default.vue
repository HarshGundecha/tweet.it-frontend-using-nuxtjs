<template>
  <div class="wrapper">
    <Navbar />
    <!-- <MainSidebar v-if="isLoggedIn"  :mypath="this.$route.path" /> -->
    <MainSidebar :mypath="this.$route.path" />
    <!-- <ContentWrapper/> -->
    <nuxt />
    <Footer />
    <ControlSidebar />
  </div>
</template>

<script>
// import { mapGetters } from 'vuex'
// import '@/assets/dist/js/demo.js';
import Navbar from '../components/shared/Navbar'
import MainSidebar from '../components/shared/MainSidebar'
// import ContentWrapper from '../components/shared/ContentWrapper';
// import Post from '../components/Post.vue';
import ControlSidebar from '../components/shared/ControlSidebar'
import Footer from '../components/shared/Footer'

export default {
  // name: 'App',
  components: {
    Navbar,
    MainSidebar,
    // ContentWrapper,
    // Post,
    ControlSidebar,
    Footer
  }
  // computed: {
  //   ...mapGetters([
  //     // 'user',
  //     'isLoggedIn'
  //   ])
  // }
}
</script>
