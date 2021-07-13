<template>
  <div>
    <swiper ref="mySwiper" :options="swiperOption">
      <swiper-slide>
        <img class="w-100" src="../assets/images/1.png" height="200">
      </swiper-slide>
      <swiper-slide>
        <img class="w-100" src="../assets/images/2.png" height="200">
      </swiper-slide>
      <swiper-slide>
        <img class="w-100" src="../assets/images/3.png" height="200">
      </swiper-slide>
      <div class="swiper-pagination pagination-home text-right px-3 pb-1" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>

export default {
  data () {
    return {
      swiperOption: {
        pagination: {
          el: '.pagination-home',
        },
      }
    }
  },

  computed: {
    swiper() {
      return this.$refs.mySwiper.$swiper
    }
  },

  mounted () {
    console.log('Current Swiper instance object', this.swiper)
    this.swiper.slideTo(3, 1000, false)
  },

  methods: {

  }
}
</script>

<style lang="scss">
@import '../assets/scss/variables';

.pagination-home {
  .swiper-pagination-bullet {
    opacity: 1;
    border-radius: .153846rem;
    background: map-get($colors, 'white');
    &.swiper-pagination-bullet-active {
      background: map-get($colors, 'info');
    }
  }
}
</style>
