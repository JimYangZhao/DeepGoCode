<template>
  <v-app>
    <!-- 头像 -->
    <!-- <v-app-bar app color="primary" dark>
      <v-avatar>
        <img src="../src/assets/zyphoto.jpeg" alt="John" />
      </v-avatar>
    </v-app-bar> -->

    <v-main>
      <!-- 标题 -->
      <PageTitle />
      <!-- 步骤 -->
      <StepsChart />
      <!-- 可以加Footer -->
      <!-- <Footer /> -->
    </v-main>
  </v-app>
</template>

<script>
import StepsChart from './components/StepsChart';
import PageTitle from './components/PageTitle';
// import Footer from './components/Footer';

export default {
  name: 'App',

  components: {
    StepsChart,
    PageTitle,
    // Footer,
  },

  data() {
    //
  },
};
</script>
<style>
p {
  color: rgb(160, 159, 159);
}
</style>
