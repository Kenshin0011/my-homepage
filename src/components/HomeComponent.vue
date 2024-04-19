<template>
  <v-carousel
      cycle
      height="300"
      hide-delimiter-background
      show-arrows-on-hover="true"
  >
    <v-carousel-item
        v-for="(slide, i) in slides"
        :key="i"
    >
      <v-sheet
          :style="`background-image: url('${slide}'); background-size: cover; background-position: center;`"
          height="100%"
          width="100vw"
      >
        <div class="d-flex fill-height justify-center align-center">
          <div class="text-h2 name">
            Kenshin Nakanishi
          </div>
        </div>
      </v-sheet>
    </v-carousel-item>
  </v-carousel>
</template>

<script>
export default {
  data () {
    return {
      slides: [
        '../../public/images/1.JPG',
        '../../public/images/2.JPG',
        '../../public/images/3.jpg',
        '../../public/images/4.jpg',
      ],
    }
  },
}
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.name {
  color: #ffffff;
}
</style>
