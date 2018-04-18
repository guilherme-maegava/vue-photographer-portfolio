<template>
  <v-container id="main_container" fluid px-0 py-0>
    <v-layout row wrap>
      <v-flex xs12 sm5 md4 lg2 px-2 py-2>
        <h2 class="text-xs-center text-sm-left">Caio Brum <v-icon large color="black">photo_camera</v-icon></h2>
      </v-flex>
      <v-flex xs12 sm7 md8 lg10 class="text-xs-center text-sm-right">
          <v-btn small="" fab flat href="https://www.facebook.com/caiogbrum?hc_ref=ARTaz6j3GvikrpH5RDRZugTvbHETU6XC00vTIeszRmhHGoP6L7tjxkZGjYcugiK7DXY">
            <v-icon large>fab fa-facebook-square</v-icon>
          </v-btn>
          <v-btn small fab flat href="https://twitter.com/caio_brum">
            <v-icon large>fab fa-twitter</v-icon>
          </v-btn>
          <v-btn small fab flat href="https://www.instagram.com/caiogbrum/">
            <v-icon large>fab fa-instagram</v-icon>
          </v-btn>
          <v-btn small fab flat>
            <v-icon large>fab fa-linkedin</v-icon>
          </v-btn>
      </v-flex>
    </v-layout>
    <v-slide-y-transition mode="out-in">
      <v-layout column align-center>
        <v-carousel>
          <v-carousel-item v-for="(item,i) in items" :src="item.src" :key="i"></v-carousel-item>
        </v-carousel>
      </v-layout>
    </v-slide-y-transition>
  </v-container>
</template>

<script>
  export default {
    data () {
      return {
        items: [
          {src: '/static/img/img1.jpg'},
          {src: '/static/img/img2.jpg'},
          {src: '/static/img/img3.jpg'},
          {src: '/static/img/img4.jpg'}
        ]
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.carousel {
  height: 580px;
}
.jumbotron__image {
  width: 100%;
  height: auto;
}
#main_container {
  max-width: 1260px;
}
</style>
